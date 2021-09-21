Homework 5
================

### Setup

``` r
# Load the tidyverse
library(tidyverse) 

# Look at the data
glimpse(diamonds)
```

    ## Rows: 53,940
    ## Columns: 10
    ## $ carat   <dbl> 0.23, 0.21, 0.23, 0.29, 0.31, 0.24, 0.24, 0.26, 0.22, 0.23, 0.…
    ## $ cut     <ord> Ideal, Premium, Good, Premium, Good, Very Good, Very Good, Ver…
    ## $ color   <ord> E, E, E, I, J, J, I, H, E, H, J, J, F, J, E, E, I, J, J, J, I,…
    ## $ clarity <ord> SI2, SI1, VS1, VS2, SI2, VVS2, VVS1, SI1, VS2, VS1, SI1, VS1, …
    ## $ depth   <dbl> 61.5, 59.8, 56.9, 62.4, 63.3, 62.8, 62.3, 61.9, 65.1, 59.4, 64…
    ## $ table   <dbl> 55, 61, 65, 58, 58, 57, 57, 55, 61, 61, 55, 56, 61, 54, 62, 58…
    ## $ price   <int> 326, 326, 327, 334, 335, 336, 336, 337, 337, 338, 339, 340, 34…
    ## $ x       <dbl> 3.95, 3.89, 4.05, 4.20, 4.34, 3.94, 3.95, 4.07, 3.87, 4.00, 4.…
    ## $ y       <dbl> 3.98, 3.84, 4.07, 4.23, 4.35, 3.96, 3.98, 4.11, 3.78, 4.05, 4.…
    ## $ z       <dbl> 2.43, 2.31, 2.31, 2.63, 2.75, 2.48, 2.47, 2.53, 2.49, 2.39, 2.…

### 1. Print a data frame that contains the simple count of diamonds in each cut

``` r
# count(group_by(diamonds,cut))
# piped:
cut_summary <- diamonds %>%
                group_by(cut) %>%
                  count()
cut_summary
```

    ## # A tibble: 5 × 2
    ## # Groups:   cut [5]
    ##   cut           n
    ##   <ord>     <int>
    ## 1 Fair       1610
    ## 2 Good       4906
    ## 3 Very Good 12082
    ## 4 Premium   13791
    ## 5 Ideal     21551

### 2. Use dplyr to create a df that contains 1% of the rows of `diamonds`, randomly subsetted

``` r
random_subset <- diamonds %>%
                  slice_sample(prop = 0.01) 
# slices out a random selection of rows, 0.01 the size of the original data frame

glimpse(random_subset)
```

    ## Rows: 539
    ## Columns: 10
    ## $ carat   <dbl> 0.91, 1.10, 1.02, 0.51, 1.01, 0.33, 0.32, 0.59, 0.43, 0.91, 0.…
    ## $ cut     <ord> Fair, Premium, Premium, Very Good, Good, Premium, Premium, Pre…
    ## $ color   <ord> F, H, G, D, G, E, G, D, D, F, E, E, H, E, D, G, G, I, F, D, D,…
    ## $ clarity <ord> VS2, VS1, VS2, VS2, SI2, VS2, SI2, VVS2, SI1, SI1, VS1, VVS2, …
    ## $ depth   <dbl> 58.0, 61.3, 62.7, 61.1, 61.1, 61.5, 62.7, 62.6, 61.0, 62.1, 60…
    ## $ table   <dbl> 56, 58, 58, 59, 62, 59, 58, 58, 57, 56, 57, 59, 57, 55, 57, 57…
    ## $ price   <int> 4474, 5673, 6169, 1787, 3948, 723, 421, 2515, 993, 4204, 3420,…
    ## $ x       <dbl> 6.34, 6.66, 6.45, 5.12, 6.38, 4.42, 4.35, 5.34, 4.88, 6.24, 5.…
    ## $ y       <dbl> 6.41, 6.61, 6.40, 5.16, 6.48, 4.46, 4.39, 5.40, 4.85, 6.20, 5.…
    ## $ z       <dbl> 3.70, 4.07, 4.03, 3.14, 3.93, 2.73, 2.74, 3.36, 2.97, 3.86, 3.…

### 3. Calculate the average size of the 100 largest diamonds in each clarity category

``` r
largest.by.clarity <- diamonds %>%
                      group_by(clarity) %>%
                      slice_max(carat, n = 100, with_ties = FALSE) %>%  # takes the 100 top values by carat
                      summarise(mean.size = mean(carat, na.rm = TRUE))  # makes a summary df of average carats

largest.by.clarity
```

    ## # A tibble: 8 × 2
    ##   clarity mean.size
    ##   <ord>       <dbl>
    ## 1 I1           2.51
    ## 2 SI2          2.62
    ## 3 SI1          2.30
    ## 4 VS2          2.23
    ## 5 VS1          2.10
    ## 6 VVS2         1.66
    ## 7 VVS1         1.51
    ## 8 IF           1.40

### 4. Make scatterplots of dimensions

``` r
# First, a plot of x vs. y
ggplot(diamonds) +
  geom_point(mapping = aes(x = x, y = y)) +
  labs(x = "Length (mm)", y = "Width (mm)")
```

![](hw_5_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

``` r
# Next, a plot of x vs. z
ggplot(diamonds) +
  geom_point(mapping = aes(x = x, y = z)) +
  labs(x = "Length (mm)", y = "Depth (mm)")
```

![](hw_5_files/figure-gfm/unnamed-chunk-5-2.png)<!-- -->

### 5. Create a new data frame, with these questionable points removed

``` r
sans_outliers <- diamonds %>%
                  filter(x > 3 & y < 50 & z < 30) # filtering out the most extreme outliers in the plots above
```

I left some less extreme outliers because I dunno what’s normal for
diamonds. Maybe they can be long and skinny like a hotdog? I doubt it
but I do hope so
