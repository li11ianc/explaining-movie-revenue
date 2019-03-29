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
popularity (variable = popularity)
    rate?

## Section 2. Data analysis plan

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
  summarise(meanpop = mean(popularity))
```

    ## # A tibble: 1 x 1
    ##   meanpop
    ##     <dbl>
    ## 1    21.5

## Section 3. Data
