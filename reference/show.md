# Show an Object

Display the object, by printing, plotting or whatever suits its class.
This function exists to be specialized by methods. The default method
calls showDefault.

## Usage

``` r
# S4 method for class 'extent_crs'
show(object)

# S4 method for class 'records'
show(object)

# S4 method for class 'rtoi'
show(object)

# S4 method for class 'variables'
show(object)
```

## Arguments

- object:

  Any R object

## Value

show returns an invisible NULL.

## Examples

``` r
if (FALSE) { # \dontrun{
## load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

## The method will now be used for automatic printing of navarre
navarre

## get records
rcds <- records(navarre)

rcds
} # }
```
