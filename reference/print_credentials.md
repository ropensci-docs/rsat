# Prints the credentials for the web services

Prints the credentials for the web services

## Usage

``` r
print_credentials(...)

# S4 method for class 'ANY'
print_credentials()
```

## Arguments

- ...:

  additional arguments.

## Value

print the credentials asigned in the package environment variable

## Examples

``` r
print_credentials()
#>      Api_name    Portal      Username Password
#> [1,] "lpdaac"    "earthdata" ""       ""      
#> [2,] "usgs"      "earthdata" ""       ""      
#> [3,] "dataspace" "dataspace" ""       ""      
set_credentials("example", "example", "earthdata")
print_credentials()
#>      Api_name    Portal      Username  Password 
#> [1,] "lpdaac"    "earthdata" "example" "example"
#> [2,] "usgs"      "earthdata" "example" "example"
#> [3,] "dataspace" "dataspace" ""        ""       
```
