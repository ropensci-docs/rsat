# Reads an rtoi from the hard drive

Reads an rtoi from the hard drive

## Usage

``` r
read_rtoi(path, ...)

# S4 method for class 'character'
read_rtoi(path, ...)
```

## Arguments

- path:

  an rtoi object.

- ...:

  additional arguments.

## Value

rtoi object readed from disk.

## Examples

``` r
if (FALSE) { # \dontrun{
library(rsat)

# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))
print(navarre)
} # }
```
