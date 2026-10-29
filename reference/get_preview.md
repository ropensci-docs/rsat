# Extract the url of the preview

It returns a character vector of urls to preview the data records.

## Usage

``` r
get_preview(x)

# S4 method for class 'records'
get_preview(x)

# S4 method for class 'records'
get_download(x)
```

## Arguments

- x:

  a `records` object.

## Value

preview url of a records

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

# get a vector with the preview url of each record
get_api_name(rcds)
} # }
```
