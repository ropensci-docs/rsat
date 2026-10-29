# Download the images from a `records` or an `rtoi` object

The function saves the raw images in the database or the specified
directory. It skips the images that already exist in the database or
directory.

## Usage

``` r
rsat_download(x, ...)

# S4 method for class 'rtoi'
rsat_download(x, db_path, verbose = FALSE, parallel = FALSE, ...)

# S4 method for class 'records'
rsat_download(x, db_path, verbose = FALSE, parallel = FALSE, ...)
```

## Arguments

- x:

  a `records` or an `rtoi` object.

- ...:

  additional arguments.

- db_path:

  path to the database. By default, the path is defined by the `rtoi`.

- verbose:

  logical argument. If `TRUE`, the function prints the running steps and
  warnings.

- parallel:

  logical argument. If `TRUE`, the function downloads from multiples
  APIs in parallel.

## Value

nothing. Downloads the images into your database

## Examples

``` r
if (FALSE) { # \dontrun{
library(rsat)

# create a copy of navarre in temp file
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

# load example rtoi
navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

# assign the path of the database
set_database(file.path(tempdir(),"DATABASE"))
rsat_download(navarre)

rcrds <-  records(navarre)

rsat_download(rcrds)
} # }
```
