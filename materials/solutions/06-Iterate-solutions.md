Iteration (solutions)
================

``` r
library(tidyverse)
```

    ## ── Attaching packages ──────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.2.0     ✔ purrr   0.3.2
    ## ✔ tibble  2.1.3     ✔ dplyr   0.8.3
    ## ✔ tidyr   1.0.0     ✔ stringr 1.4.0
    ## ✔ readr   1.1.1     ✔ forcats 0.4.0

    ## ── Conflicts ─────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
# Toy data
set.seed(1000)
exams <- list(
  student1 = round(runif(10, 50, 100)),
  student2 = round(runif(10, 50, 100)),
  student3 = round(runif(10, 50, 100)),
  student4 = round(runif(10, 50, 100)),
  student5 = round(runif(10, 50, 100))
)

extra_credit <- list(0, 0, 10, 10, 15)
```

## Your Turn 1

What kind of object is `mod`? Why are models stored as this kind of
object?

``` r
mod <- lm(price ~ carat + cut + color + clarity, data = diamonds)
# View(mod)
```

`mod` is a list. A list is used because we need to store lots of
heterogeneous information.

## Quiz

What’s the difference between a list and an **atomic** vector?

Atomic vectors are: “logical”, “integer”, “numeric” (synonym “double”),
“complex”, “character” and “raw” vectors.

Lists can hold data of different types and different lengths, we can
even put lists inside other lists.

## Your Turn 2

Here is a list:

``` r
a_list <- list(num = c(8, 9), 
            log = TRUE,    
            cha = c("a", "b", "c"))
```

Here are two subsetting commands. Do they return the same values? Run
the code chunk above, *and then* run the code chunks below to confirm

``` r
a_list["num"]
```

    ## $num
    ## [1] 8 9

``` r
a_list$num
```

    ## [1] 8 9

## Your Turn 3

What will each of these return? Run the code chunks to confirm.

``` r
vec <- c(-2, -1, 0, 1, 2)
abs(vec)
```

    ## [1] 2 1 0 1 2

`abs()` returns the absolute value of each element.

``` r
lst <- list(-2, -1, 0, 1, 2)
abs(lst)
```

    ## Error in abs(lst): non-numeric argument to mathematical function

Out intent might be to take the absolute value of each element, but we
get an error, because `abs()` doens’t know how to handle a list.

## Your Turn 4

Run the code in the chunks. What does it return?

``` r
list(student1 = mean(exams$student1),
     student2 = mean(exams$student2),
     student3 = mean(exams$student3),
     student4 = mean(exams$student4),
     student5 = mean(exams$student5))
```

    ## $student1
    ## [1] 71.4
    ## 
    ## $student2
    ## [1] 74.6
    ## 
    ## $student3
    ## [1] 70.2
    ## 
    ## $student4
    ## [1] 75.1
    ## 
    ## $student5
    ## [1] 79.1

This chunk manually iterates over the elements of `exams` taking the
mean of each element, and returning the results in a list.

``` r
library(purrr)
map(exams, mean)
```

    ## $student1
    ## [1] 71.4
    ## 
    ## $student2
    ## [1] 74.6
    ## 
    ## $student3
    ## [1] 70.2
    ## 
    ## $student4
    ## [1] 75.1
    ## 
    ## $student5
    ## [1] 79.1

This does the exact same thing, but automatically.

## Your Turn 5

Calculate the variance (`var()`) of each student’s exam grades.

``` r
exams %>% map(var)
```

    ## $student1
    ## [1] 174.0444
    ## 
    ## $student2
    ## [1] 194.7111
    ## 
    ## $student3
    ## [1] 216.8444
    ## 
    ## $student4
    ## [1] 227.2111
    ## 
    ## $student5
    ## [1] 167.6556

## Your Turn 6

Calculate the max grade (max())for each student. Return the result as a
vector.

``` r
exams %>% map_dbl(max)
```

    ## student1 student2 student3 student4 student5 
    ##       88       93       91       98      100

## Your Turn 7

Write a function that counts the best exam twice and then takes the
average. Use it to grade all of the students.

1.  Write code that solves the problem for a real object  
2.  Wrap the code in `function(){}` to save it  
3.  Add the name of the real object as the function argument

<!-- end list -->

``` r
double_best <- function(x) {
  (sum(x) + max(x)) / (length(x) + 1)
}

exams %>%
  map_dbl(double_best)
```

    ## student1 student2 student3 student4 student5 
    ## 72.90909 76.27273 72.09091 77.18182 81.00000

### Your Turn 8

Compute a final grade for each student, where the final grade is the
average test score plus any `extra_credit` assigned to the student.
Return the results as a double (i.e. numeric) vector.

``` r
exams %>% 
  map2_dbl(extra_credit, function(x, y) mean(x) + y)
```

    ## student1 student2 student3 student4 student5 
    ##     71.4     74.6     80.2     85.1     94.1

-----

# Take Aways

Lists are a useful way to organize data, but you need to arrange
manually for functions to iterate over the elements of a list.

You can do this with the `map()` family of functions in the purrr
package.

To write a function,

1.  Write code that solves the problem for a real object  
2.  Wrap the code in `function(){}` to save it  
3.  Add the name of the real object as the function argument

This sequence will help prevent bugs in your code (and reduce the time
you spend correcting
bugs).

<!-- This file by Charlotte Wickham is licensed under a Creative Commons Attribution 4.0 International License, adapted from the orignal work at https://github.com/rstudio/master-the-tidyverse by RStudio. -->
