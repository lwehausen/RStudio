Cubs\_Data\_Analysis\_Viz
================
Lauren Wehausen
9/1/2022

First, let’s load the data:

``` r
cubs <- read.csv("https://raw.githubusercontent.com/gjm112/DSCI401/main/data/cubs_all_time.csv")
```

Now, let’s take a look at the data we’re working with:

``` r
head(cubs, 3)
```

    ##   Year           Tm         Lg   G  W  L Ties  W.L. pythW.L.   Finish   GB
    ## 1 2022 Chicago Cubs NL Central 125 54 71    0 0.432    0.436 3rd of 5 18.0
    ## 2 2021 Chicago Cubs NL Central 162 71 91    0 0.438    0.421 4th of 5 24.0
    ## 3 2020 Chicago Cubs NL Central  60 34 26    0 0.567    0.545 1st of 5   --
    ##          Playoffs   R  RA Attendance BatAge PAge X.Bat X.P        Top.Player
    ## 1                 518 596    2163550   28.1 29.8    57  37   N.Hoerner (4.2)
    ## 2                 705 839    1978934   29.1 29.4    69  40 W.Contreras (4.1)
    ## 3 Lost NLWC (2-0) 265 240         NA   27.9 30.3    47  26   Y.Darvish (2.8)
    ##         Managers
    ## 1 D.Ross (54-71)
    ## 2 D.Ross (71-91)
    ## 3 D.Ross (34-26)

How many total games have the Cubs won and lost between 1876 and 2022?

``` r
sum(cubs$W)
```

    ## [1] 11141

``` r
sum(cubs$L)
```

    ## [1] 10592

Total games won: 11141 Total games lost: 10592

What year did the Cubs score the most runs? What year did the Cubs score
the fewest runs? Do you have any thoughts about the year that the Cubs
scored the fewest runs?

``` r
#Find the maximum number of runs.
max(cubs$R)
```

    ## [1] 1056

``` r
#Find what year the value found previously, occurred. 
cubs$Year[which.max(cubs$R)]
```

    ## [1] 1894

``` r
#Find the minimum number of runs.
min(cubs$R)
```

    ## [1] 265

``` r
#Determine what year the previously found value occurred. 
cubs$Year[which.min(cubs$R)]
```

    ## [1] 2020

The Cubs had the most runs, 1056, in 1894 and the least runs, 265, in
2020. The year 2020 was probably the worst because it was when COVID
first began.

In how many seasons was the Cubs total attendance (i.e. the variable
Attendance) over 3 million?

``` r
attend2 <- cubs$Attendance[!is.na(cubs$Attendance)] 
sum(attend2 > 3000000)
```

    ## [1] 12

There were 12 seasons where the attendance was greater than or equal to
3 million.
