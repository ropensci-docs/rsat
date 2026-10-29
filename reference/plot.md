# Plot an `rtoi` object

Plot (a map of) the values of an `rtoi` or `records` object.

## Usage

``` r
# S4 method for class 'rtoi,Date'
plot(
  x,
  y,
  ...,
  variable = "rgb",
  band_name = c("red", "green", "blue"),
  verbose = FALSE,
  xsize = 250,
  ysize = 250
)

# S4 method for class 'rtoi,character'
plot(
  x,
  y,
  ...,
  variable = "rgb",
  product = "ALL",
  band_name = c("red", "green", "blue"),
  dates = NULL,
  verbose = FALSE,
  xsize = 250,
  ysize = 250
)

# S4 method for class 'records,ANY'
plot(x, y, verbose = FALSE, ...)

# S4 method for class 'rtoi,missing'
plot(x, y, verbose = FALSE, ...)
```

## Arguments

- x:

  an `rtoi` or `records`.

- y:

  character argument. The valid values are "dates", "preview", or
  "view".

- ...:

  additional arguments.

- variable:

  character argument. The variable to be plotted. By default, a color
  (RGB) variable is selected .

- band_name:

  character vector argument. Enables false color plots. By default,
  usual bands are selected `c("red","green","blue")`.

- verbose:

  logical argument. If `TRUE`, the function prints the running steps and
  warnings.

- xsize:

  the number of samples on the horizontal axis.

- ysize:

  the number of samples on the vertical axis.

- product:

  character argument. The product name to be plotted.

- dates:

  date vector argument. The dates to be plotted.

## Value

`tmap` plot.

## Examples

``` r
library(rsat)
 if (FALSE) { # \dontrun{

# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

print(navarre)

# plot the calendar
plot(navarre, "dates")



# replace with your own "username" and "password"
set_credentials("username", "password")

# plot the quicklook images before the download
# needs credentials to download preview images
plot(navarre, y = "preview")

# select partially cloud free
rcds <- records(navarre)
rcds <- rcds[dates(rcds) %in% as.Date(c("20210310", "20210313"), "%Y%m%d")]
records(navarre) <- rcds

plot(navarre, "preview")

file.copy(from=system.file("ex/Pamplona",package="rsat"),
         to=tempdir(),
         recursive = TRUE)
# plot already mosaicked rtoi ("view" mode)
pamplona <- read_rtoi(file.path(tempdir(),"Pamplona"))

rsat_list_data(pamplona)

# plot can compute the rgb image on the fly from mosaicek bands
plot(pamplona, "view", product="mod09ga")

# plot on the fly with false color
plot(pamplona, "view",
     product = "mod09ga",
     band_name = c("nir", "red", "green"))

file.copy(from=system.file("ex/PamplonaDerived",package="rsat"),
         to=tempdir(),
         recursive = TRUE)
# plot already mosaicked rtoi ("view" mode)
pamplona.derived <- read_rtoi(file.path(tempdir(),"PamplonaDerived"))

rsat_list_data(pamplona.derived)

# plot derived variables
plot(pamplona.derived, "view",
     product = "mod09ga",
     variable = "NDVI")

# Set the max and min value in plot
plot(pamplona.derived,"view",
     variable="NDVI",
     product="mod09ga",
     zlim=c(0,1))
} # }
```
