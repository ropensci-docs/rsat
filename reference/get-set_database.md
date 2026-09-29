# Extracts or assign the path of the database

Extracts the path to the database from an rtoi/package environment. If
both, environment and rtoi database are defined the rtoi database is
used.

## Usage

``` r
get_database(x)

# S4 method for class 'rtoi'
get_database(x)

# S4 method for class 'missing'
get_database()

set_database(x, ...)

# S4 method for class 'rtoi'
set_database(x, value)

# S4 method for class 'character'
set_database(x)
```

## Arguments

- x:

  an rtoi object.

- ...:

  additional arguments.

- value:

  character argument. The value for change the database directory of x.

## Value

the database path of an rtoi

## Examples

``` r
if (FALSE) { # \dontrun{
# load example rtoi
file.copy(from=system.file("ex/Navarre",package="rsat"),
         to=tempdir(),
         recursive = TRUE)

navarre <- read_rtoi(file.path(tempdir(),"Navarre"))

# get the databse used by navarre
get_database(navarre)

# set the a new database path
set_database(navarre,"new_path")

# get the database used by rsat by default
get_database()

# set the a new database path for the entire environment
set_database("new_path")
} # }
```
