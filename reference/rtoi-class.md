# Region and Time Of Interest (`rtoi`)

It is a proxy object to store metadata about satellite imagery covering
a spatial region over a time period. Images can come from multiple
missions/programs and its purpose is to help managing heterogeneous
datasets.

## Details

An `rtoi` object manages two main folders called database and rtoi. The
database is meant to work as a local, generic, and organized archive of
raw satellite data retrieved with the `download()` function. The rtoi
folder contains processed information for a particular region and time
of interest. When
[`mosaic()`](https://rspatial.github.io/terra/reference/mosaic.html) is
called, the function crops and mosaics the relevant raw images from the
database and saves the results in the rtoi folder. This folder also
contains a `region.rtoi` file which saves metadata about the region/time
of interest and satellite imagery available.

## Fields

- `name`:

  a character with the name of the region of interest.

- `rtoi_path`:

  a character with the path to the rtoi folder.

- `region`:

  an sf with the region of interest.

- `records`:

  the satellite records available for your region and time of interest.

- `db_path`:

  a character with the path to the database.

## Examples

``` r
if (FALSE) { # \dontrun{
data(ex.navarre)
## Create an rtoi with database
# path where the region is stored
rtoi.path <- tempdir()

# path where downloads are stored
db.path <- file.path(tempdir(), "DATABASE")
navarre <- new_rtoi(
  name = "Navarre_rtoi",
  region = ex.navarre,
  rtoi_path = rtoi.path,
  db_path = db.path
)

print(navarre)

## Create an rtoi without database
navarre2 <- new_rtoi(
  name = "Navarre_rtoi2",
  region = ex.navarre,
  rtoi_path = rtoi.path
)

print(navarre2)
} # }
```
