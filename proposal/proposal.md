PROJECT TITLE
================
NAME HERE
TODAY’S DATE

## Section 1. Introduction

The dataset we are using is “TMBD 5000 Movie Dataset.”

Originally, we found this set on kaggle.com. The data originates from
“The Movie Database” API, it was collected from this original dataset.

The data’s variables: budget genres homepage id keywords
original\_language original\_title overview popularity
production\_companies production\_countries release\_date revenue
runtime spoken\_languages status tagline title vote\_average Vote\_count

Our research question would be, what variables correlate to a high
revenue rate?

## Section 2. Data analysis plan

The outcome would be popularity, and predictors would include but not be
limited to the following variables: budget, production\_companies,
keywords, spoken\_languages, original\_language, release\_date, and
revenue.

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.1.0     ✔ purrr   0.2.5
    ## ✔ tibble  2.0.0     ✔ dplyr   0.7.8
    ## ✔ tidyr   0.8.2     ✔ stringr 1.3.1
    ## ✔ readr   1.3.1     ✔ forcats 0.3.0

    ## ── Conflicts ────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
movies <- read_csv("tmdb_5000_movies.csv")
```

``` r
movies %>%
  summarise(meanrev = mean(revenue)) 
```

    ## # A tibble: 1 x 1
    ##     meanrev
    ##       <dbl>
    ## 1 82260639.

This is the average revenue for all the movies in the dataset. We would
consider a movie to have a high revenue if they are greater than the
average.

``` r
movies %>%
  ggplot(mapping= aes(original_language, log(revenue))) +
  geom_boxplot() +
  coord_flip()
```

    ## Warning: Removed 1427 rows containing non-finite values (stat_boxplot).

![](proposal_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

## Section 3. Data
