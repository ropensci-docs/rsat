# Get the file path of a `records` or an `rtoi`

Get the file path of a `records` or an `rtoi`

## Usage

``` r
get_dir(x)

# S4 method for class 'records'
get_dir(x)

# S4 method for class 'records'
get_order(x)

# S4 method for class 'rtoi'
get_dir(x)
```

## Arguments

- x:

  .

## Value

the file path in the records

## Examples

``` r
if (FALSE) { # \dontrun{
# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

# get the path of the
get_dir(navarre)

# get the records
rcds <- records(navarre)

# gets the relative path to store records data
get_dir(rcds)
} # }
```
