# Length of an object

Get or set the length of vectors (including lists) and factors, and of
any other R object for which a method has been defined.

## Usage

``` r
# S4 method for class 'extent_crs'
length(x)

# S4 method for class 'records'
length(x)
```

## Arguments

- x:

  a `records` object to compute its length.

## Value

Length currently returns a non-negative integer of length 1

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

length(rcds)
} # }
```
