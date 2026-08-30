# Extracts region from an rtoi

gets the sf that specifies the region of an rtoi.

## Usage

``` r
region(x)

# S4 method for class 'rtoi'
region(x)

region(x) <- value

# S4 method for class 'rtoi,sf'
region(x) <- value

# S4 method for class 'rtoi,`NULL`'
region(x) <- value
```

## Arguments

- x:

  an rtoi object.

- value:

  an sf object to define the region in x.

## Value

the sf class with the region of an rtoi

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

# get the region from rtoi
sf.obj <-  region(navarre)
plot(sf.obj)

# asign new region value
region(navarre)<-NULL

region(navarre)<-sf.obj
} # }
```
