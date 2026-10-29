# Get/set the dates from a `records` or an `rtoi`

Get/set the dates from a `records` or an `rtoi`

## Usage

``` r
dates(x)

# S4 method for class 'records'
dates(x)

dates(x) <- value

# S4 method for class 'records'
dates(x) <- value

# S4 method for class 'rtoi'
dates(x)
```

## Arguments

- x:

  a `records` or an `rtoi` object.

- value:

  the new date to asign

## Value

returns a vector of `Date` class

## Examples

``` r
if (FALSE) { # \dontrun{
# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

# get a vector of dates includes in rtoi
dates(navarre)

# get the records
rcds <- records(navarre)

# coerce the records to dataframr
dates(rcds)
} # }
```
