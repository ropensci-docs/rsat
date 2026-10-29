# List the variables and satellites supported by `rsat`

Displays the satellites and variable method

## Usage

``` r
show_variables(...)

# S4 method for class 'ANY'
show_variables()
```

## Arguments

- ...:

  arguments for nesting functions

## Value

prints supported satellites and derived variables information.

## Examples

``` r
show_variables()
#> Data and variable methods provided by rsat
#> Satellite products: ls1, ls2, ls3, ls4, ls5, ls7, ls8, mod09ga, myd09ga, mcd43a4, Sentinel-1, Sentinel-2, Sentinel-3, SY_2_SYN___.
#> Variable Methods: EVI, MSAVI2, NBR, NBR2, NDMI, NDVI, NDWI, RGB, SAVI.
```
