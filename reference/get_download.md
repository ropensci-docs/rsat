# Extract the url to download a data record

It returns a character with the url to download the image.

## Usage

``` r
get_download(x)
```

## Arguments

- x:

  a `records` object.

## Value

download url of a records

## Examples

``` r
if (FALSE) { # \dontrun{
# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

# get the records
rcds <- records(navarre)
# coerce the records to rtoi
get_download(rcds)
} # }
```
