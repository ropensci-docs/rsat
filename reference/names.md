# Get the name of the object

A function to get or set the names of an object.

## Usage

``` r
# S4 method for class 'records'
names(x)

# S4 method for class 'rtoi'
names(x)

# S4 method for class 'rtoi,character'
names(x) <- value
```

## Arguments

- x:

  a `records` or an `rtoi` object.

- value:

  character argument. The new value for `x`.

## Value

a character vector containing the name of all the names in `x`.

## Examples

``` r
if (FALSE) { # \dontrun{
# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

names(navarre)
names(navarre) <- "New name"
names(navarre)

rcrds <- records(navarre)

names(rcrds)
} # }
```
