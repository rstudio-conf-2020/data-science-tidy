Introduction to Data Science in the Tidyverse
================

### rstudio::conf 2020

by Amelia McNamara and Hadley Wickham

-----

:spiral_calendar: January 27 and 28, 2020  
:alarm_clock:     09:00 - 17:00  
:hotel:           \[ADD ROOM\]  
:writing_hand:    [rstd.io/conf](http://rstd.io/conf)

-----

## Overview

This is a two-day, hands-on workshop designed for people who are brand new to R & RStudio and who learn best in person. 

You will learn the basics of R and data science, and practice using the RStudio IDE (integrated development environment). We'll discuss much of the material from the book R for Data Science, including data visualization (ggplot2), data transformation and tidying (dplyr, tidyr), understanding special data types (stringr, forcats, lubridate), and modeling (broom). Throughout the workshop, we'll work in RMarkdown documents, and learn best practices for data computing.

If you want to transition from coding in base R to the tidyverse, or just jump into doing data science in the tidyverse without any prior R experience, this is the workshop for you! We will have a team of TAs on hand to show you the ropes, and help you out when you get stuck.


## Learning objectives

The basics of doing data science in the tidyverse, including data visualization, data transformation and tidying, understanding special data types, and basic modeling.

## Is this course for me?

Consider these questions:

1. You have a dataset of prices of diamonds, as well as their size. Could you make a scatterplot of the two variables using ggplot2?

2. You have two datasets, one with information on music genres and age ranges, the other with genres and radio station call names. Can you imagine how you would join them together with a dplyr verb?

3. We want to model the wages of people in the United States, using their height and education as predictors. Then, we would like to plot model predictions for each level of educational attainment. Can you imagine how to do this in R?

If you answered "no" to any/all of those questions... great! This workshop is for you. By the end of the two days, you should be able to accomplish all those tasks. If you answered "yes" to all three questions, you may want to consider taking a different workshop.

## Prework

You'll be using [RStudio Cloud](https://rstudio.cloud/), a cloud-based version of R and RStudio available through your web browser.  So (all going well) on the day of the workshop all you'll need is **a laptop that can access the internet** (wifi will be available).  Please do [sign up for an account on RStudio Cloud](https://client.login.rstudio.cloud/oauth/register?redirect=https%3A%2F%2Fclient.login.rstudio.cloud%2Foauth%2Flogin%3Fshow_auth%3D0%26show_login%3D1%26show_setup%3D1) before the workshop. You can make an account directly on RStudio Cloud, or use single-sign-on with a service like GitHub or Google. 

In the unlikely event that there are problems with the conference internet connection, you may want to have a local installation on your computer as a backup. If you'd like, install the following:
 
1. A recent version of R (~3.6), which is available for free at [cran.r-project.org](http://www.cran.r-project.org)
2. A recent version of RStudio IDE (~1.2.5033), available for free at [www.rstudio.com/download](http://www.rstudio.com/download)
3. The set of relevant R packages, which you can install by connecting to the internet, opening RStudio, and running:  
 
    install.packages(c("babynames", "fivethirtyeight", "formatR", "gapminder", "hexbin", "mgcv", "maps", "mapproj", "nycflights13", "rmarkdown", "skimr", "tidyverse", "viridis")) 

Don't forget to bring your power cord!

## Schedule

| Time          | Activity         |
| :------------ | :--------------- |
| 09:00 - 10:30 | Session 1        |
| 10:30 - 11:00 | *Coffee break*   |
| 11:00 - 12:30 | Session 2        |
| 12:00 - 13:30 | *Lunch break*    |
| 13:30 - 15:00 | Session 3        |
| 15:00 - 15:30 | *Coffee break*   |
| 15:30 - 17:00 | Session 4        |

## Instructors

Amelia McNamara (she/her) is an assistant professor of statistics in the Department of Computer and Information Sciences at the University of St Thomas, in Minnesota. She is an RStudio [Certified Trainor](https://education.rstudio.com/trainers/), as well as a Carpentries [Certified Instructor](https://carpentries.org/instructors/). This is her third year teaching an rstudio::conf workshop. 

-   [amelia.mn](http://www.amelia.mn)
-   @[AmeliaMN](http://www.twitter.com/AmeliaMN)

Hadley Wickham (he/him) is the Chief Scientist at RStudio. He is the author of many R packages, including major components of the tidyverse, including ggplot2, dplyr, tidyr, purrr, and readr. He is also the author of the book [R for Data Science](https://r4ds.had.co.nz/) with Garrett Grolemund, on which much of this workshop is based. 

- [github.com/hadley](http://github.com/hadley)
- @[hadleywickham](https://twitter.com/hadleywickham)

## TAs

We have a fantastic slate of TAs assisting at this workshop! They are:

- Jesse Mostipak
- Ben Baumer
- Matthew Flickinger
- Mike Smith

-----

![](https://i.creativecommons.org/l/by/4.0/88x31.png) This work is
licensed under a [Creative Commons Attribution 4.0 International
License](https://creativecommons.org/licenses/by/4.0/).
