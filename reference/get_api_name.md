# Get the API name of a `records`

A function to get or set the api names of an object.

## Usage

``` r
get_api_name(x)

# S4 method for class 'records'
get_api_name(x)
```

## Arguments

- x:

  a `records` object.

## Value

a character vector containing the API names of the elements in `x`.

## Examples

``` r
if (FALSE) { # \dontrun{
# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

# get the records
rcds <- records(navarre)

# get a vector with the api name of each records
get_api_name(rcds)
} # }
```
