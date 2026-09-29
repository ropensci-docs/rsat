# Mosaic the tiles intersecting the region of interest

Satellite measurements are divided into indivisible units called tiles.
The mosaic function binds and crops the tiles to generate a single image
of the region of interest for each date.

## Usage

``` r
rsat_mosaic(x, ...)

# S4 method for class 'rtoi'
rsat_mosaic(x, ...)

# S4 method for class 'records'
rsat_mosaic(
  x,
  out_path,
  db_path,
  bfilter = c(),
  warp = "extent",
  region,
  overwrite = FALSE,
  verbose = FALSE,
  ...
)
```

## Arguments

- x:

  an `rtoi` object.

- ...:

  additional arguments.

- out_path:

  path to save the mosaicked images. By default, the path is defined by
  `x`.

- db_path:

  path to the database. By default, the path is defined by `x`.

- bfilter:

  a vector of bands to. If not supplied, all are used.

- warp:

  character. If equal to "extent", it also crops the images around the
  `rtoi`. Use "" otherwise.

- region:

  an sf object. Region for cropping the images around. By default, the
  path is defined by `x`.

- overwrite:

  logical argument. If `TRUE`, overwrites the existing images with the
  same name.

- verbose:

  boolean. If TRUE show verbose output. Default FALSE

## Value

nothing. Mosaics the downloaded images and stored them on the hard disk

## Examples

``` r
if (FALSE) { # \dontrun{
library(rsat)

# load navarre sf from the package
data(ex.navarre)

# set the credentials
set_credentials("username", "password")

# path where the region is stored
rtoi.path <- tempdir()
# path where downloads are stored
db.path <- file.path(tempdir(), "DATABASE")
navarre <- new_rtoi(
  "Navarre",
  ex.navarre,
  rtoi.path,
  db.path
) #'
# Landsat-5
rsat_search(
  region = navarre,
  product = "LANDSAT_TM_C1",
  dates = as.Date("1988-08-01") + seq(1, 35)
)
rsat_download(navarre)

rsat_mosaic(navarre, overwrite = T)

rsat_list_data(navarre)
} # }
```
