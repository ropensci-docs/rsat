# List the information available for an `rtoi`

Displays the existing products, bands, and processing levels for a given
`rtoi`

## Usage

``` r
rsat_list_data(x, ...)

# S4 method for class 'rtoi'
rsat_list_data(x, ...)
```

## Arguments

- x:

  an `rtoi` object.

- ...:

  additional arguments.

## Value

a `data.frame` of the available information.

## Examples

``` r
if (FALSE) { # \dontrun{
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

# load example rtoi
navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

print(navarre)

# print empty rtoi
rsat_list_data(navarre)

file.copy(from=system.file("ex/Pamplona",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

# load example rtoi
pamplona <- read_rtoi(file.path(tempdir(),"Pamplona"))

print(pamplona)

rtoi.data <- rsat_list_data(pamplona)
# print mosaicked bands
print(rtoi.data)

# print mosaicked bands + derived NDVI
file.copy(from=system.file("ex/PamplonaDerived",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

# load example rtoi
pamplona.derived <- read_rtoi(file.path(tempdir(),"PamplonaDerived"))
rsat_list_data(pamplona.derived)
} # }
```
