# Search for keywords in OWID catalog data

This function searches for a vector of keywords within specified columns
of an OWID catalog data frame. If no columns are specified, it searches
all character and factor columns.

## Usage

``` r
owid_search(data, keywords, columns = NULL)
```

## Arguments

- data:

  A data frame, typically obtained from
  [owid_get_catalog](https://econdataverse.github.io/r-owidapi/reference/owid_get_catalog.md).

- keywords:

  A character vector of one or more keywords to search for. The search
  is case-insensitive.

- columns:

  An optional character vector of column names to search within. If NULL
  (default), all character and factor columns are searched.

## Value

A filtered data frame containing only rows that match at least one of
the keywords in at least one of the specified columns.

## Examples

``` r
# \donttest{
# Get the OWID catalog
catalog <- owid_get_catalog()

# owid_get_catalog() returns NULL if the API is unreachable
if (!is.null(catalog)) {
  # Search for climate or carbon in all text columns
  print(owid_search(catalog, c("climate", "carbon")))

  # Search only in the title column
  print(owid_search(catalog, c("climate", "carbon"), c("title")))
}
#> # A tibble: 199 × 17
#>    rowid    id config_id        is_inheritance_enabled force_datapage created_at
#>    <int> <int> <chr>            <lgl>                  <lgl>          <date>    
#>  1   361   488 0191b6c7-37aa-7… TRUE                   FALSE          2017-04-07
#>  2   362   530 0191b6c7-37ce-7… TRUE                   FALSE          2017-04-19
#>  3   487   784 0191b6c7-38c5-7… FALSE                  FALSE          2017-07-22
#>  4   728  1108 0191b6c7-3a46-7… FALSE                  FALSE          2017-09-08
#>  5    90  1129 0191b6c7-3a55-7… FALSE                  FALSE          2017-09-10
#>  6   534  1277 0191b6c7-3aeb-7… FALSE                  FALSE          2017-10-05
#>  7   600  1362 0191b6c7-3b27-7… FALSE                  FALSE          2017-10-14
#>  8   731  1366 0191b6c7-3b2a-7… FALSE                  FALSE          2017-10-15
#>  9   604  1421 0191b6c7-3b5f-7… FALSE                  FALSE          2017-10-23
#> 10  1632  2245 0191b6c7-3e77-7… FALSE                  FALSE          2018-02-20
#> # ℹ 189 more rows
#> # ℹ 11 more variables: updated_at <date>, last_edited_at <date>,
#> #   published_at <date>, config <chr>, slug <chr>, type <chr>, title <chr>,
#> #   subtitle <chr>, note <chr>, title_plus_variant <chr>, is_published <lgl>
#> # A tibble: 41 × 17
#>    rowid    id config_id        is_inheritance_enabled force_datapage created_at
#>    <int> <int> <chr>            <lgl>                  <lgl>          <date>    
#>  1   362   530 0191b6c7-37ce-7… TRUE                   FALSE          2017-04-19
#>  2   487   784 0191b6c7-38c5-7… FALSE                  FALSE          2017-07-22
#>  3   731  1366 0191b6c7-3b2a-7… FALSE                  FALSE          2017-10-15
#>  4  1177  2823 0191b6c7-4123-7… FALSE                  FALSE          2018-06-25
#>  5  2525  3302 0191b6c7-4367-7… FALSE                  FALSE          2019-02-03
#>  6  2539  4135 0191b6c7-4716-7… FALSE                  FALSE          2020-04-17
#>  7  2011  4305 0191b6c7-47a7-7… FALSE                  FALSE          2020-07-12
#>  8  1780  4331 0191b6c7-47c1-7… TRUE                   FALSE          2020-07-21
#>  9  2013  4374 0191b6c7-4811-7… FALSE                  FALSE          2020-07-30
#> 10  2015  4413 0191b6c7-4851-7… FALSE                  FALSE          2020-08-03
#> # ℹ 31 more rows
#> # ℹ 11 more variables: updated_at <date>, last_edited_at <date>,
#> #   published_at <date>, config <chr>, slug <chr>, type <chr>, title <chr>,
#> #   subtitle <chr>, note <chr>, title_plus_variant <chr>, is_published <lgl>
# }
```
