# Preview a `records` or an `rtoi` object

Preview a `records` or an `rtoi` object

## Usage

``` r
rsat_preview(x, n, ...)

# S4 method for class 'rtoi,Date'
rsat_preview(x, n, lpos = c(3, 2, 1), add.layer = FALSE, verbose = FALSE, ...)

# S4 method for class 'rtoi,missing'
rsat_preview(x, n, lpos = c(3, 2, 1), add.layer = FALSE, verbose = FALSE, ...)

# S4 method for class 'records,Date'
rsat_preview(
  x,
  n,
  lpos = c(3, 2, 1),
  tmp_dir = file.path(tempdir()),
  add.layer = FALSE,
  verbose = FALSE,
  get.map = TRUE,
  ...
)

# S4 method for class 'records,numeric'
rsat_preview(
  x,
  n,
  lpos = c(3, 2, 1),
  tmp_dir = file.path(tempdir()),
  add.layer = FALSE,
  verbose = FALSE,
  get.map = TRUE,
  ...
)
```

## Arguments

- x:

  a `records` or an `rtoi` object.

- n:

  the date expressed as the temporal index in the time series.

- ...:

  additional arguments

- lpos:

  vector argument. Defines the position of the red-green-blue layers to
  enable a false color visualization.

- add.layer:

  logical argument. If `TRUE`, the function plots the image on an
  existing map.

- verbose:

  logical argument. If `TRUE`, the function prints the running steps and
  warnings.

- tmp_dir:

  character argument. The directory where preview images are located.

- get.map:

  logical argument. If `TRUE`, the function return the leaflet map.

## Value

nothing. Previews the region in the viewer.

## Examples

``` r
if (FALSE) { # \dontrun{
library(rsat)

# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

set_credentials("username", "password")
set_database(file.path(tempdir(), "DATABASE"))

# by default the first date in rtoi is previewed
rsat_preview(navarre)


preview.dates <- dates(navarre)
# use add.layer to preview images of several days
rsat_preview(navarre,preview.dates[2],add.layer = TRUE)

# you can also preview records
rcrds <- records(navarre)
rsat_preview(rcrds, n = 1)
} # }
```
