# Coerce to a Data Frame

Functions to check if an object is a data frame, or coerce it if
possible.

## Usage

``` r
# S4 method for class 'extent_crs'
as.data.frame(x)

# S4 method for class 'records'
as.data.frame(x)
```

## Arguments

- x:

  Any R object.

## Value

returns a data frame, normally with all row names

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
# coerce the records to rtoi
df <- as.data.frame(rcds)
# print the dataframe
print(df)
} # }
```
