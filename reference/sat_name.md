# Get the name of the satellite(s) from a `records` or an `rtoi`

Get the name of the satellite(s) from a `records` or an `rtoi`

## Usage

``` r
sat_name(x)

# S4 method for class 'records'
sat_name(x)

# S4 method for class 'rtoi'
sat_name(x)
```

## Arguments

- x:

  a `records` or an `rtoi` object.

## Value

the name of the satellite

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
# coerce the records to dataframe
sat_name(rcds)
} # }
```
