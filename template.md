Simple document
================

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
#incluing several packages,like reader, ggplot....
```

want to keep all things that in the same project, in this case, just
create a new folder data within the same R folder and copy all import
files into data folder—-make sure all the data files that are useful for
project in the same folder

let’s import the `FAS_litters.cvs`csv using a relative path.

``` r
litters_df=
  read_csv("data/FAS_litters.csv")
```

    ## Rows: 49 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (2): Group, Litter Number
    ## dbl (6): GD0 weight, GD18 weight, GD of Birth, Pups born alive, Pups dead @ ...
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
#readr package: sort by the library tidyverse, read_csv()functions;
#the first thing: let function where to find this file

#the paths show: when you just created a folder in your r project, this would show when you type its name
#using this relative path would not change even you transfer folder to other places

litters_df
```

    ## # A tibble: 49 × 8
    ##    Group `Litter Number` `GD0 weight` `GD18 weight` `GD of Birth`
    ##    <chr> <chr>                  <dbl>         <dbl>         <dbl>
    ##  1 Con7  #85                     19.7          34.7            20
    ##  2 Con7  #1/2/95/2               27            42              19
    ##  3 Con7  #5/5/3/83/3-3           26            41.4            19
    ##  4 Con7  #5/4/2/95/2             28.5          44.1            19
    ##  5 Con7  #4/2/95/3-3             NA            NA              20
    ##  6 Con7  #2/2/95/3-2             NA            NA              20
    ##  7 Con7  #1/5/3/83/3-3/2         NA            NA              20
    ##  8 Con8  #3/83/3-3               NA            NA              20
    ##  9 Con8  #2/95/3                 NA            NA              20
    ## 10 Con8  #3/5/2/2/95             28.5          NA              20
    ## # ℹ 39 more rows
    ## # ℹ 3 more variables: `Pups born alive` <dbl>, `Pups dead @ birth` <dbl>,
    ## #   `Pups survive` <dbl>

``` r
#do to check if this works

litters_df = 
  janitor::clean_names(litters_df)
#in the cvs, there are spaces between names, but R cannot read them, we need to change names into snack_name
#this code make all names into snack_name format

#janior is a whole package in r, have bunch of functions in it
```

Import the same dataset using an absolute path.

``` r
# problem: litters_df_abs=
#  read_csv("~/R Project/p8105_data_wrangle_1/data/FAS_litters.cvs")
#if you just use this absoluate path (when type and choose which folder that your data in), when you put the whole foler(include project and data into new folder,the path is changed, this would make mistake for this path)---get error(move folder)

# litters_df_abs


# litters_df_abs = 
#  janitor::clean_names(litters_df_abs)
```
