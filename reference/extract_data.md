# Loads into R a time series of images regarding an rtoi, satellite product, and remote sensing index.

Loads into R a time series of images regarding an rtoi, satellite
product, and remote sensing index.

## Usage

``` r
rsat_get_raster(x, p, v, s, ...)

# S4 method for class 'rtoi'
rsat_get_raster(x, p, v, s, ...)

rsat_get_SpatRaster(x, p, v, s, ...)

# S4 method for class 'rtoi'
rsat_get_SpatRaster(x, p, v, s, ...)

rsat_get_stars(x, p, v, s, ...)

# S4 method for class 'rtoi'
rsat_get_stars(x, p, v, s, ...)
```

## Arguments

- x:

  an rtoi.

- p:

  a character with the name of the satellite data product.

- v:

  a character with the name of the index.

- s:

  a character with the name of the stage wanted.

- ...:

  additional arguments.

## Value

a raster stack.

## Examples

``` r
if (FALSE) { # \dontrun{
library(rsat)
# load example rtoi
file.copy(from=system.file("ex/PamplonaDerived",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

# load example rtoi
pamplona.derived <- read_rtoi(file.path(tempdir(),"PamplonaDerived"))

# print available variables
rsat_list_data(pamplona.derived)

# get RasterStack from raster package
suppressWarnings(mod.ndvi.raster <-
           rsat_get_raster(pamplona.derived, "mod09ga", "NDVI"))
plot(mod.ndvi.raster)

# get spatraster from terra package
mod.ndvi.rast <- rsat_get_SpatRaster(pamplona.derived, "mod09ga", "NDVI")
plot(mod.ndvi.rast)

# get stars from stars package
suppressWarnings(mod.ndvi.stars <-
rsat_get_stars(pamplona.derived, "mod09ga", "NDVI"))
plot(mod.ndvi.stars)


## get any band in rtoi
# list available data
rsat_list_data(pamplona.derived)
# select band 1: MODIS_Grid_500m_2D_sur_refl_b01_1
mod.ndvi.rast <- rsat_get_SpatRaster(pamplona.derived,
                                     "mod09ga",
                                     "MODIS_Grid_500m_2D_sur_refl_b01_1")
plot(mod.ndvi.rast)
} # }
```
