# Get the slot called order from a `records` or an `rtoi`

Get the slot called order from a `records` or an `rtoi`

## Usage

``` r
get_order(x)

get_order(x) <- value

# S4 method for class 'records'
get_order(x) <- value
```

## Arguments

- x:

  a `records` or an `rtoi` object.

- value:

  logical argument. The new value for `x`.

## Value

the value of called order

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

# gets a boolean
get_order(rcds)
} # }
```
