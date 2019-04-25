PROJECT TITLE
================
Zuck(R)berg
25 April 2019

Your project goes here\! Before you submit, make sure your chunks are
turned off with `echo = FALSE`.

You can add sections as you see fit. Make sure you have a section called
Introduction at the beginning and a section called Conclusion at the
end. The rest is up to you\!

### Introduction

### Stuff

For our dataset of 5000 movies, we decided to remove the variables id,
homepage, and original\_title, since we felt that these variables did
not contribute to our research question of what contributed to a
“successful” movie. Additionally, since we found problems with the
budget and revenue variables of non-American movies (not in US dollars),
we decided to filter for only english movies as a proxy for American
movies. (Since there is no definite way to filter for only American
movies). We also filtered for movies that had a budget and revenue that
were nonzero, this is so that our data would not be skewed by movies
that were not intended to draw revenue or were not of the same budget
caliber of the rest of the films.

![](project_files/figure-gfm/popularity-explanations-1.png)<!-- -->

    ## # A tibble: 10 x 2
    ##    title                                                  popularity
    ##    <chr>                                                       <dbl>
    ##  1 Minions                                                      876.
    ##  2 Interstellar                                                 724.
    ##  3 Deadpool                                                     515.
    ##  4 Guardians of the Galaxy                                      481.
    ##  5 Mad Max: Fury Road                                           434.
    ##  6 Jurassic World                                               419.
    ##  7 Pirates of the Caribbean: The Curse of the Black Pearl       272.
    ##  8 Dawn of the Planet of the Apes                               244.
    ##  9 The Hunger Games: Mockingjay - Part 1                        206.
    ## 10 Big Hero 6                                                   204.

We are going to not look at popularity because we can’t figure out where
this came from,,, etc explain this.

    ## # A tibble: 10 x 2
    ##    title                                          budget
    ##    <chr>                                           <dbl>
    ##  1 Pirates of the Caribbean: On Stranger Tides 380000000
    ##  2 Pirates of the Caribbean: At World's End    300000000
    ##  3 Avengers: Age of Ultron                     280000000
    ##  4 Superman Returns                            270000000
    ##  5 John Carter                                 260000000
    ##  6 Tangled                                     260000000
    ##  7 Spider-Man 3                                258000000
    ##  8 The Lone Ranger                             255000000
    ##  9 The Dark Knight Rises                       250000000
    ## 10 Harry Potter and the Half-Blood Prince      250000000

    ## # A tibble: 2,516 x 1
    ##    production_companies                                                    
    ##    <chr>                                                                   
    ##  1 "[{\"name\": \"Ingenious Film Partners\", \"id\": 289}, {\"name\": \"Tw…
    ##  2 "[{\"name\": \"Walt Disney Pictures\", \"id\": 2}, {\"name\": \"Jerry B…
    ##  3 "[{\"name\": \"Columbia Pictures\", \"id\": 5}, {\"name\": \"Danjaq\", …
    ##  4 "[{\"name\": \"Legendary Pictures\", \"id\": 923}, {\"name\": \"Warner …
    ##  5 "[{\"name\": \"Walt Disney Pictures\", \"id\": 2}]"                     
    ##  6 "[{\"name\": \"Columbia Pictures\", \"id\": 5}, {\"name\": \"Laura Zisk…
    ##  7 "[{\"name\": \"Walt Disney Pictures\", \"id\": 2}, {\"name\": \"Walt Di…
    ##  8 "[{\"name\": \"Marvel Studios\", \"id\": 420}, {\"name\": \"Prime Focus…
    ##  9 "[{\"name\": \"Warner Bros.\", \"id\": 6194}, {\"name\": \"Heyday Films…
    ## 10 "[{\"name\": \"DC Comics\", \"id\": 429}, {\"name\": \"Atlas Entertainm…
    ## # … with 2,506 more rows

### Creating a “Profitability” Variables

The first profitability variable is a ratio of revenue to budget, to
show by what percentage a movie was “profitable.” This second
profitability variable is a categorical variable that deciphers if the
movie was profitable or not, based on the profitiability ratio. If the
ratio was greater than 1, it was considered profitable. It will simply
say “yes” for profitable, and “no” for non-profitable.

    ## # A tibble: 3,086 x 19
    ##    budget genres keywords original_langua… overview popularity
    ##     <dbl> <chr>  <chr>    <chr>            <chr>         <dbl>
    ##  1 2.37e8 "[{\"… "[{\"id… en               In the …      150. 
    ##  2 3.00e8 "[{\"… "[{\"id… en               Captain…      139. 
    ##  3 2.45e8 "[{\"… "[{\"id… en               A crypt…      107. 
    ##  4 2.50e8 "[{\"… "[{\"id… en               Followi…      112. 
    ##  5 2.60e8 "[{\"… "[{\"id… en               John Ca…       43.9
    ##  6 2.58e8 "[{\"… "[{\"id… en               The see…      116. 
    ##  7 2.60e8 "[{\"… "[{\"id… en               When th…       48.7
    ##  8 2.80e8 "[{\"… "[{\"id… en               When To…      134. 
    ##  9 2.50e8 "[{\"… "[{\"id… en               As Harr…       98.9
    ## 10 2.50e8 "[{\"… "[{\"id… en               Fearing…      156. 
    ## # … with 3,076 more rows, and 13 more variables:
    ## #   production_companies <chr>, production_countries <chr>,
    ## #   release_date <date>, revenue <dbl>, runtime <dbl>,
    ## #   spoken_languages <chr>, status <chr>, tagline <chr>, title <chr>,
    ## #   vote_average <dbl>, vote_count <dbl>, pratio <dbl>, profit <chr>

### Making a Categorical “spoken languages” Variable

Here, we will be creating a new vategorical variable, that signifies if
the only language spoken in the film is english, or not. If the only
spoken language is english, the value will be “yes,” if there are other
languages spoken or english is not used, the value will be “no.”

### Splitting date variable

### Genre trends

![](project_files/figure-gfm/genre-trends-1.png)<!-- -->

![](project_files/figure-gfm/horror-1.png)<!-- -->

![](project_files/figure-gfm/action-1.png)<!-- -->

![](project_files/figure-gfm/action-count-1.png)<!-- -->

### Title and Profitability

![](project_files/figure-gfm/title-len-1.png)<!-- -->

### Making a variable for holiday releases

### Making a variable for likely sequels

### Making a variable for major production companies

Major production companies according to Wikipedia are Universal Pictures
(NBCUniversal), Paramount Pictures (Viacom), WarnerBros. Pictures
(WarnerMedia), Walt Disney Pictures (Walt Disney Studios), Columbia
Pictures (Sony Pictures) (in the format Major film studio unit (Studio
parent) from
<https://en.wikipedia.org/wiki/Major_film_studio#Present_2>).

### Making a variable for tagline length

    ## # A tibble: 3,086 x 31
    ##    budget genres keywords original_langua… overview popularity
    ##     <dbl> <chr>  <chr>    <chr>            <chr>         <dbl>
    ##  1 2.37e8 "[{\"… "[{\"id… en               In the …      150. 
    ##  2 3.00e8 "[{\"… "[{\"id… en               Captain…      139. 
    ##  3 2.45e8 "[{\"… "[{\"id… en               A crypt…      107. 
    ##  4 2.50e8 "[{\"… "[{\"id… en               Followi…      112. 
    ##  5 2.60e8 "[{\"… "[{\"id… en               John Ca…       43.9
    ##  6 2.58e8 "[{\"… "[{\"id… en               The see…      116. 
    ##  7 2.60e8 "[{\"… "[{\"id… en               When th…       48.7
    ##  8 2.80e8 "[{\"… "[{\"id… en               When To…      134. 
    ##  9 2.50e8 "[{\"… "[{\"id… en               As Harr…       98.9
    ## 10 2.50e8 "[{\"… "[{\"id… en               Fearing…      156. 
    ## # … with 3,076 more rows, and 25 more variables:
    ## #   production_companies <chr>, production_countries <chr>, year <dbl>,
    ## #   month <dbl>, day <dbl>, revenue <dbl>, runtime <dbl>,
    ## #   spoken_languages <chr>, status <chr>, tagline <chr>, title <chr>,
    ## #   vote_average <dbl>, vote_count <dbl>, pratio <dbl>, profit <chr>,
    ## #   spokenlength <int>, english <chr>, horror <chr>, action <chr>,
    ## #   oneword <chr>, holiday_release <chr>, likely_sequel <chr>,
    ## #   if_major <chr>, major_productionco <chr>, tag_length <int>

### Making a preliminary linear model

We aim to find an ideal linear model to predict profitability ratio
based on a variety of factors; before constructing our model, we will
remove observations that lack values for these factors.

We filter the dataset to remove movies with NA values so that our
backwards model selection will work (the only NAs in the values we are
considering are for tagline length)

    ## 
    ## Call:
    ## lm(formula = pratio ~ holiday_release + likely_sequel + budget + 
    ##     if_major + major_productionco + tag_length + english + horror + 
    ##     budget * if_major + likely_sequel * budget, data = movies_filt)
    ## 
    ## Coefficients:
    ##                  (Intercept)            holiday_releaseyes  
    ##                    6.123e+00                    -1.099e+00  
    ##             likely_sequelyes                        budget  
    ##                   -1.918e+00                    -6.337e-08  
    ##                  if_majoryes       major_productionco20thc  
    ##                   -3.205e-01                     1.631e+00  
    ##   major_productioncocolumbia      major_productioncodisney  
    ##                   -8.398e-01                     1.154e+00  
    ## major_productioncodreamworks   major_productioncolionsgate  
    ##                    1.806e-01                    -1.425e+00  
    ##     major_productioncomarvel   major_productioncoparamount  
    ##                    2.111e+00                     1.533e+00  
    ##      major_productioncopixar   major_productioncouniversal  
    ##                    5.068e+00                     1.244e+00  
    ##     major_productioncowarner                    tag_length  
    ##                           NA                    -9.931e-04  
    ##                   englishyes                     horroryes  
    ##                    6.019e-01                     1.741e+00  
    ##           budget:if_majoryes       likely_sequelyes:budget  
    ##                    2.344e-08                     3.370e-08

    ## # A tibble: 19 x 2
    ##    term                              estimate
    ##    <chr>                                <dbl>
    ##  1 (Intercept)                   6.12        
    ##  2 holiday_releaseyes           -1.10        
    ##  3 likely_sequelyes             -1.92        
    ##  4 budget                       -0.0000000634
    ##  5 if_majoryes                  -0.321       
    ##  6 major_productionco20thc       1.63        
    ##  7 major_productioncocolumbia   -0.840       
    ##  8 major_productioncodisney      1.15        
    ##  9 major_productioncodreamworks  0.181       
    ## 10 major_productioncolionsgate  -1.43        
    ## 11 major_productioncomarvel      2.11        
    ## 12 major_productioncoparamount   1.53        
    ## 13 major_productioncopixar       5.07        
    ## 14 major_productioncouniversal   1.24        
    ## 15 tag_length                   -0.000993    
    ## 16 englishyes                    0.602       
    ## 17 horroryes                     1.74        
    ## 18 budget:if_majoryes            0.0000000234
    ## 19 likely_sequelyes:budget       0.0000000337

We fit a regression model to predict pulse rate based on
holiday\_release, likely\_sequel, budget, if\_major,
major\_productionco, tag\_length, english, horror, the interaction
between budget and likely\_sequel, and the interaction between budget
and if\_major. We chose to examine the those interactions because
whether a movie is a sequel (and thus has a known revenue for its
precedents and some expectation that people will see it) may be related
to its budget and also the relation between budget and having access to
the resources we assume accompany a major production company may also be
related in an interesting way.

Linear Model:

Profitability Ratio = 6.1229785 + -1.0990405(Holiday Release) +
-1.9180928(Likely Sequel) + -6.336645410^{-8}(Budget) + -0.3205203(Major
Production Company) + 1.6309264(20th Century Fox) 1.6309264(Columbia) +
+ 1.6309264(Disney) + 1.6309264(DreamWorks) + 1.6309264(Lionsgate) +
1.6309264(Marvel) + -0.8397983(Paramount) + 1.6309264(Pixar) +
1.1544246(Universal) + 0.1805623(Warner) + -1.4251867(Tagline Length) +
2.1110122(Spoken Language English) + 1.5332836(Horror) +
5.0676815(Budget \* Major Production Company) + 1.2435644(Likely Sequel
\* Budget)

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic  p.value    df  logLik    AIC
    ##       <dbl>         <dbl> <dbl>     <dbl>    <dbl> <int>   <dbl>  <dbl>
    ## 1    0.0435        0.0374  9.83      7.21 1.78e-18    19 -10641. 21321.
    ## # … with 3 more variables: BIC <dbl>, deviance <dbl>, df.residual <int>

We compute the adjusted R-squared value for the filtered model for pulse
as 0.0374255; this is a helpful measure of the goodness of the fit of
the model.

    ## Start:  AIC=13160.15
    ## pratio ~ holiday_release + likely_sequel + budget + if_major + 
    ##     major_productionco + tag_length + english + horror + budget * 
    ##     if_major + likely_sequel * budget
    ## 
    ##                        Df Sum of Sq    RSS   AIC
    ## - major_productionco    9   1349.51 277316 13156
    ## - tag_length            1      1.55 275968 13158
    ## <none>                              275967 13160
    ## - english               1    219.85 276186 13160
    ## - holiday_release       1    415.51 276382 13162
    ## - budget:if_major       1    526.82 276493 13164
    ## - horror                1    782.40 276749 13166
    ## - likely_sequel:budget  1   1133.45 277100 13170
    ## 
    ## Step:  AIC=13156.18
    ## pratio ~ holiday_release + likely_sequel + budget + if_major + 
    ##     tag_length + english + horror + budget:if_major + likely_sequel:budget
    ## 
    ##                        Df Sum of Sq    RSS   AIC
    ## - tag_length            1      4.00 277320 13154
    ## <none>                              277316 13156
    ## - english               1    212.74 277529 13156
    ## - holiday_release       1    383.42 277699 13158
    ## - budget:if_major       1    559.79 277876 13160
    ## - horror                1    731.69 278048 13162
    ## - likely_sequel:budget  1   1194.52 278511 13166
    ## 
    ## Step:  AIC=13154.22
    ## pratio ~ holiday_release + likely_sequel + budget + if_major + 
    ##     english + horror + budget:if_major + likely_sequel:budget
    ## 
    ##                        Df Sum of Sq    RSS   AIC
    ## <none>                              277320 13154
    ## - english               1    217.16 277537 13154
    ## - holiday_release       1    382.41 277702 13156
    ## - budget:if_major       1    562.24 277882 13158
    ## - horror                1    744.78 278065 13160
    ## - likely_sequel:budget  1   1191.73 278512 13164

    ## # A tibble: 9 x 2
    ##   term                         estimate
    ##   <chr>                           <dbl>
    ## 1 (Intercept)              6.08        
    ## 2 holiday_releaseyes      -1.05        
    ## 3 likely_sequelyes        -1.77        
    ## 4 budget                  -0.0000000637
    ## 5 if_majoryes              0.269       
    ## 6 englishyes               0.596       
    ## 7 horroryes                1.69        
    ## 8 budget:if_majoryes       0.0000000239
    ## 9 likely_sequelyes:budget  0.0000000340

We perform backwards model selection based on AIC, Akaike Information
Criterion (another measure of the fit of a model), and obtain the best
fit.

Selected Linear Model:

Profitability Ratio = 6.0806711 + -1.0517342(Holiday Release) +
-1.7689054(Likely Sequel) + -6.368522610^{-8}(Budget) +
0.26903(Columbia) + 0.5956686(Disney) + 1.6865216(Paramount) +
2.386509710^{-8}(Universal) + 3.397361210^{-8}(Warner) +
-1.4251867(Spoken Language English) + 2.1110122(Horror) +
1.5332836(Likely Sequel \* Budget)

    ## [1] 21321.05

    ## [1] 21315.12

Our AIC value decreases for the selected model, which indicates that it
is a better fit. Thus factors of holiday\_release, likely\_sequel,
budget, ETC TYPE THE REST HERE are the best predictors of profitability.

    ## [1] 0.03876268

Our R-squared value of 0.0387627 for our final selected model indicates
that 3.8762682% of the variation in Profitability can be well-explained
by a linear relationship with INSERT LIST HERE

### Conclusion
