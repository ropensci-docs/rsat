# Computes a remote sensing index from an `rtoi`

Combines the bands from multispectral satellite products through simple
math to highlight a process or material in the image.

## Usage

``` r
rsat_derive(x, variable, ...)

# S4 method for class 'rtoi,character'
rsat_derive(
  x,
  variable,
  product,
  dates,
  fun,
  overwrite = FALSE,
  verbose = FALSE,
  suppressWarnings = TRUE,
  ...
)
```

## Arguments

- x:

  an `rtoi` as the source of images.

- variable:

  the name of the variable.

- ...:

  additional argument for variable deriving

- product:

  the name of the product from which the index is computed.

- dates:

  a vector of dates being considered (optional).

- fun:

  a `function` that computes the remote sensing index.

- overwrite:

  logical argument. If `TRUE`, overwrites the existing images with the
  same name.

- verbose:

  logical argument. If `TRUE`, the function prints the running steps and
  warnings.

- suppressWarnings:

  evaluates its expression in a context that ignores all warnings.

## Value

nothing. The derived variables will be save in the hard drive. Use
get_stars to get the variables.

## Details

The package contemplates some pre-defined indexes, which can be
displayed using the
[`show_variables()`](https://docs.ropensci.org/rsat/reference/show_variables.md)
function. To compute one of those, write its name in the `variable`
argument. Custom indexes can be supplied through the `fun` argument. The
function should use the name of the bands as inputs (red, green, blue,
nir, swir1, or swir2) and return a single element. For instance, the
Normalized Difference Snow Index would be;

NDSI = function(green, swir1){ ndsi \<- (green - swir1)/(green + swir1)
return(ndsi) }

## Examples

``` r
if (FALSE) { # \dontrun{
library(rsat)

# create a copy of pamplona in temp file
file.copy(from=system.file("ex/Pamplona",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

# load example rtoi
pamplona <- read_rtoi(file.path(tempdir(),"Pamplona"))

rsat_list_data(pamplona)
# show prefedined varibles
show_variables()
rsat_derive(pamplona, "NDVI", product = "mod09ga")
# now NDVI is processed
rsat_list_data(pamplona)

# ad-hoc variable
NDSI = function(green, swir1){
  ndsi <- (green - swir1)/(green + swir1)
  return(ndsi)
}
rsat_derive(pamplona, "NDSI", product = "mod09ga",fun=NDSI)
# now NDVI is processed
rsat_list_data(pamplona)
plot(pamplona, product="mod09ga",variable="NDSI")
} # }
```
