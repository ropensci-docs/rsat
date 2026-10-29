# Create a new `records` object

Create a new `records` object from scratch

## Usage

``` r
new_record(
  sat,
  name,
  date,
  product,
  download,
  file_path,
  path,
  row,
  tileid,
  preview,
  api_name,
  order,
  extent_crs
)

# S4 method for class 'character,character,Date,character,character,character,numeric,numeric,character,character,character,logical,extent_crs'
new_record(
  sat,
  name,
  date,
  product,
  download,
  file_path,
  path,
  row,
  tileid,
  preview,
  api_name,
  order,
  extent_crs
)

# S4 method for class 'character,character,Date,character,character,character,numeric,numeric,character,character,character,logical,missing'
new_record(
  sat,
  name,
  date,
  product,
  download,
  file_path,
  path,
  row,
  tileid,
  preview,
  api_name,
  order
)
```

## Arguments

- sat:

  the name of the satellite to which the record belongs.

- name:

  the name of the record.

- date:

  the date of the record.

- product:

  the product.

- download:

  the url to download the satellite record.

- file_path:

  the saving directory for the satellite record.

- path:

  the path of the tiling system.

- row:

  the row of the tiling system.

- tileid:

  the tile id.

- preview:

  the url of the preview of the satellite record.

- api_name:

  the api name.

- order:

  boolean, defines if the image must be requested or not.

- extent_crs:

  extent (used to project the preview).

## Value

records object

## Examples

``` r
if (FALSE) { # \dontrun{
# create a new record from scrach
rcds <- new_record(
  sat = "modis",
  name = "mod09a",
  date = as.Date("2011087", "%Y%j"),
  product = "product",
  download = "url/aaa/download",
  file_path = "file_path",
  path = 1,
  row = 1,
  tileid = "exampleid",
  preview = "url",
  api_name = "nasa_inventory",
  order = FALSE
)
rcds
} # }
```
