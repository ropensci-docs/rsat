# Extracts the satellite records

returns the object records from an rtoi.

## Usage

``` r
records(x)

# S4 method for class 'rtoi'
records(x)

records(x) <- value

# S4 method for class 'rtoi,records'
records(x) <- value
```

## Arguments

- x:

  an rtoi object

- value:

  a records object to be set to x.

## Value

a set of records in x rtoi

## Examples

``` r
if (FALSE) { # \dontrun{
#' library(rsat)
# create a copy of navarre
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)
# load example rtoi
navarre <- read_rtoi(file.path(tempdir(),"Navarre"))
print(navarre)

rcrds <- records(navarre)

records(navarre)<-rcrds[1]
print(navarre)

records(navarre) <- rcrds
print(navarre)
unlink(file.path(tempdir(),"Navarre"),recursive=TRUE)
} # }
```
