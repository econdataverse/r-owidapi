# Download data catalog of Our World in Data

Downloads the data catalog of Our World in Data (OWID) hosted on
Datasette. The catalog is retrieved page by page, so the complete set of
charts is returned rather than just the first page.

## Usage

``` r
owid_get_catalog(snake_case = TRUE)
```

## Arguments

- snake_case:

  Logical. If TRUE (default), converts column names to lowercase.

## Value

A tibble containing the OWID catalog, with one row per chart.

## Examples

``` r
# \donttest{
# Download a full table
owid_get_catalog()
#> # A tibble: 4,276 × 17
#>    rowid    id config_id        is_inheritance_enabled force_datapage created_at
#>    <int> <int> <chr>            <lgl>                  <lgl>          <date>    
#>  1    51    20 0191b6c7-3629-7… FALSE                  FALSE          2015-07-02
#>  2   285    27 0191b6c7-3633-7… FALSE                  FALSE          2015-07-07
#>  3   131    31 0191b6c7-3635-7… FALSE                  FALSE          2015-07-09
#>  4   745    44 0191b6c7-3638-7… FALSE                  FALSE          2015-07-18
#>  5   437    46 0191b6c7-363d-7… FALSE                  FALSE          2015-07-20
#>  6   397    51 0191b6c7-3645-7… FALSE                  FALSE          2015-07-21
#>  7   424    52 0191b6c7-3647-7… FALSE                  FALSE          2015-07-22
#>  8   132    56 0191b6c7-364c-7… FALSE                  FALSE          2015-07-24
#>  9   370    64 0191b6c7-364e-7… FALSE                  FALSE          2015-07-31
#> 10   438    73 0191b6c7-3653-7… FALSE                  FALSE          2015-08-05
#> # ℹ 4,266 more rows
#> # ℹ 11 more variables: updated_at <date>, last_edited_at <date>,
#> #   published_at <date>, config <chr>, slug <chr>, type <chr>, title <chr>,
#> #   subtitle <chr>, note <chr>, title_plus_variant <chr>, is_published <lgl>
# }
```
