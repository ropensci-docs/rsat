# A class object for satellite image metadata

This class object organizes the attributes of satellite images' metadata
from several missions/programs uniformly. Structuring the information
facilitates managing, previewing, and downloading data records.

## Details

`records` works as vector. It accepts usual R methods such as `c`, `[]`,
[`length()`](https://rdrr.io/r/base/length.html),
[`subset()`](https://rdrr.io/r/base/subset.html) or
[`unique()`](https://docs.ropensci.org/rsat/reference/unique.md). Each
record (vector element) contains several parameters or slots.

The object can be coerced into a `data.frame` by using the function
[`as.data.frame()`](https://rdrr.io/r/base/as.data.frame.html). The
`data.frame` can be transformed back into a `records` with the function
[`as.records()`](https://docs.ropensci.org/rsat/reference/as.records.md).

## Slots

- `sat`:

  the name of the satellite.

- `name`:

  the name of the file.

- `date`:

  capturing date of the image.

- `product`:

  name of the data product.

- `path`:

  the path of the tiling system.

- `row`:

  the row of the tiling system.

- `tileid`:

  the tile identification number.

- `download`:

  the download url.

- `file_path`:

  the saving directory for the satellite record.

- `preview`:

  the preview url.

- `api_name`:

  the name of the API.

- `order`:

  boolean, whether the image needs to be ordered.

- `extent_crs`:

  coordinate reference system of the preview.

## Examples

``` r
if (FALSE) { # \dontrun{
library(rsat)
# create a copy of navarre
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

# load example rtoi
navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

rcrds <- records(navarre)

modis.rcrds <- rcrds[sat_name(rcrds)%in%"Modis"]
ls8.rcrds <- rcrds[sat_name(rcrds)%in%"Landsat-8"]

class(modis.rcrds)
dates(ls8.rcrds)
modis.ls8.records <- c(ls8.rcrds, modis.rcrds)

print(modis.ls8.records)
} # }
```
