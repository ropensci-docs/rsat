# Saves the credentials for the web services

Saves the credentials for the web services

## Usage

``` r
set_credentials(user, pass, credential)

# S4 method for class 'character,character,missing'
set_credentials(user, pass)

# S4 method for class 'character,character,character'
set_credentials(user, pass, credential)
```

## Arguments

- user:

  character argument. Defines the username of an api platform to search
  or download images

- pass:

  character argument. Defines the password of an api platform to search
  and download images

- credential:

  optional argument to specify the name of the platform. Valid names are
  earthdata, scihub, scihubs5p, or ALL

## Value

nothing. set the credentials in the package environment variable

## Examples

``` r
print_credentials()
#>      Api_name    Portal      Username  Password 
#> [1,] "lpdaac"    "earthdata" "example" "example"
#> [2,] "usgs"      "earthdata" "example" "example"
#> [3,] "dataspace" "dataspace" ""        ""       
set_credentials("example", "example")
print_credentials()
#>      Api_name    Portal      Username  Password 
#> [1,] "lpdaac"    "earthdata" "example" "example"
#> [2,] "usgs"      "earthdata" "example" "example"
#> [3,] "dataspace" "dataspace" "example" "example"
set_credentials("example", "example", "earthdata")
print_credentials()
#>      Api_name    Portal      Username  Password 
#> [1,] "lpdaac"    "earthdata" "example" "example"
#> [2,] "usgs"      "earthdata" "example" "example"
#> [3,] "dataspace" "dataspace" "example" "example"
```
