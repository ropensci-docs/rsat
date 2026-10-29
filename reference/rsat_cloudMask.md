# Create cloud mask from an rtoi

Create cloud mask from an rtoi

## Usage

``` r
rsat_cloudMask(x, ...)

# S4 method for class 'rtoi'
rsat_cloudMask(x, products = "ALL", verbose = FALSE, overwrite = FALSE, ...)
```

## Arguments

- x:

  rtoi object from which cloud masks are computed.

- ...:

  additional arguments

- products:

  the name of the dataset from which cloud masks are computed.

- verbose:

  logical argument. If `TRUE`, the function prints the running steps and
  warnings.

- overwrite:

  logical argument. If `TRUE`, overwrites the existing images with the
  same name.

## Value

nothing. The cloud masks will be save in the hard drive. Use get_stars
to get the variables.

## Examples

``` r
if (FALSE) { # \dontrun{
## Smooth data in rtoi
library(rsat)

# create a copy of pamplona in temp file
file.copy(from=system.file("ex/Pamplona",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

# load example rtoi
pamplona <- read_rtoi(file.path(tempdir(),"Pamplona"))

rsat_cloudMask(pamplona)

rsat_list_data(pamplona)
} # }
```
