# Prints the values

prints an object and returns it invisibly (via invisible(x)).

## Usage

``` r
# S4 method for class 'api_dataspace'
print(x)

# S4 method for class 'api_lpdaac'
print(x)

# S4 method for class 'api_usgs'
print(x)

# S4 method for class 'extent_crs'
print(x)

# S4 method for class 'records'
print(x)

# S4 method for class 'rtoi'
print(x)

# S4 method for class 'variables'
print(x, ...)
```

## Arguments

- x:

  an object to be printed..

- ...:

  additional arguments.

## Value

prints rtoi metadata

## Examples

``` r
if (FALSE) { # \dontrun{
library(rsat)

# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

print(navarre)

# get records
rcrds <- records(navarre)

print(rcrds)
} # }
```
