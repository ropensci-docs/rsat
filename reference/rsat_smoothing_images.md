# Fill data gaps and smooth outliers in a time series of satellite images

`apply_ima` is the implementation of a spatio-temporal method called
Interpolation of Mean Anomalies(IMA) for gap filling and smoothing
satellite data (Militino et al. 2019) . `smoothing_images` is the
implementation of a spatio temporal method called image mean anomaly
(IMA) for gap filling and smoothing satellite data (Militino et al.
2019) .

## Usage

``` r
rsat_smoothing_images(x, method, ...)

# S4 method for class 'rtoi,character'
rsat_smoothing_images(
  x,
  method,
  product = "ALL",
  satellite = "ALL",
  stage = "ALL",
  variable = "ALL",
  test.mode = FALSE,
  ...
)

# S4 method for class 'SpatRaster,character'
rsat_smoothing_images(x, method, ...)
```

## Arguments

- x:

  `rtoi` or `RastespatRaster` containing a time series of satellite
  images.

- method:

  character argument. Defines the method used for processing the images,
  e.a. "IMA".

- ...:

  arguments for nested functions:

  - `Img2Fill` a `vector` defining the images to be filled/smoothed.

  - `r.dates` a `vector` of dates for the layers in `x`. Mandatory when
    layer names of `x` do not contain their capturing dates "`YYYYJJJ`"
    format.

  - `nDays` a `numeric` argument with the number of previous and
    subsequent days of the temporal neighborhood.

  - `nYears` a `numeric` argument with the number of previous and
    subsequent years of the temporal neighborhood.

  - `aFilter` a `vector` of lower and upper quantiles defining the
    outliers in the anomalies. Ex. c(0.05,0.95).

  - `fact` a `numeric` argument specifying the aggregation factor of the
    anomalies.

  - `fun` a `function` used to aggregate the image of anomalies. Both
    `mean` (default) or `median` are accepted.

  - `snow.mode` logical argument. If `TRUE`, the process is parallelized
    using the functionalities from the \` `raster`' package.

  - `predictSE` calculate the standard error instead the prediction.

  - `factSE` the `fact` used in the standard error prediction.

  - `out.name` the name of the folder containing the smoothed/filled
    images when saved in the Hard Disk Device (HDD).

  - `only.na` logical argument. If `TRUE` only fills the `NA` values.
    `FALSE` by default.

- product:

  character argument. The name of the product to be processed. Check the
  name of the parameter with
  [`rsat_list_data`](https://docs.ropensci.org/rsat/reference/rsat_list_data.md)
  function. Check the name of the parameter with
  [`rsat_list_data`](https://docs.ropensci.org/rsat/reference/rsat_list_data.md)
  function. By default, "ALL".

- satellite:

  character argument. The name of the satellite to be processed. Check
  the name of the parameter with
  [`rsat_list_data`](https://docs.ropensci.org/rsat/reference/rsat_list_data.md)
  function. By default, "ALL".

- stage:

  character argument. The name of the processed stage of the data. Check
  the name of the parameter with
  [`rsat_list_data`](https://docs.ropensci.org/rsat/reference/rsat_list_data.md)
  function. By default, "ALL".

- variable:

  character argument.The name of the variable to be processed. Check the
  name of the parameter with
  [`rsat_list_data`](https://docs.ropensci.org/rsat/reference/rsat_list_data.md)
  function. By default, "ALL".

- test.mode:

  logical argument. If `TRUE`, the function runs some lines to test
  `rsat_smoothing_images` with rtoi object.

## Value

a `RastespatRaster` with the filled/smoothed images.

## Details

This filling/smoothing method was developed by Militino et al. (2019) .
IMA fills the gaps borrowing information from an adaptable temporal
neighborhood. Two parameters determine the size of the neighborhood; the
number of days before and after the target image (`nDays`) and the
number of previous and subsequent years (`nYears`). Both parameters
should be adjusted based on the temporal resolution of the of the
time-series of images. We recommend that the neighborhood extends over
days rather than years, when there is little resemblance between
seasons. Also, cloudy series may require larger neighborhoods.

IMA gives the following steps; (1) creates a representative image from
the temporal neighborhood of the target image (image to be
filled/smoothed) e.g., doing the mean, median, etc. for each pixel's
time-series (`fun`), (2) the target and representative images are
subtracted giving an image of anomalies, (3) the anomalies falling
outside the quantile limits (`aFilter`) are considered outliers and
therefore removed, (4) it aggregates the anomaly image into a coarser
resolution (`fact`) to reveal potential spatial dependencies, (5) the
procedure fits a spatial model (thin plate splines or TPS) to the
anomalies which is then used to interpolate the values at the original
resolution, and (6) the output is the sum of the interpolated anomalies
and the average image.

## References

Militino AF, Ugarte MD, Perez-Goya U, Genton MG (2019). “Interpolation
of the Mean Anomalies for Cloud-Filling in Land Surface Temperature
(LST) and Normalized Difference Vegetation Index (NDVI).” *IEEE
Transactions on Geoscience and Remote Sensing. (Open-Access)*.
<http://dx.doi.org/10.1109/TGRS.2019.2904193>.

## Examples

``` r
if (FALSE) { # \dontrun{
## Smooth data in rtoi
library(rsat)
require(terra)

# create a copy of pamplona in temp file
file.copy(from=system.file("ex/PamplonaDerived",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

# load example rtoi
pamplona <- read_rtoi(file.path(tempdir(),"PamplonaDerived"))
rsat_smoothing_images(pamplona,
                      method = "IMA",
                      variable="NDVI"
)
rsat_list_data(pamplona)
# get smoothed
smoothed <- rsat_get_SpatRaster(pamplona,p="mod09ga",v="NDVI",s="IMA")
plot(smoothed)

# get original
original <- rsat_get_SpatRaster(pamplona,p="mod09ga",v="NDVI",s="variables")
plot(original)
plot(smoothed[[1]]-original[[1]])

## smooth user defined SpatRaster dataset
require(terra)
data(ex.ndvi.navarre)

# load an example of NDVI time series in Navarre
ex.ndvi.navarre <- rast(ex.ndvi.navarre)
# the raster stack with the date in julian format as name
plot(ex.ndvi.navarre)

# smoothin and fill all the time series
tiles.mod.ndvi.filled <- rsat_smoothing_images(ex.ndvi.navarre,
  method = "IMA"
)
# show the filled images
plot(tiles.mod.ndvi.filled)

# plot comparison of the cloud and the filled images
tiles.mod.ndvi.comp <- c(
  ex.ndvi.navarre[[1]], tiles.mod.ndvi.filled[[1]],
  ex.ndvi.navarre[[2]], tiles.mod.ndvi.filled[[2]]
)
plot(tiles.mod.ndvi.comp)
} # }
```
