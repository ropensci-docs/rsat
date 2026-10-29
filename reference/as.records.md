# Create records object from data frame

Create records object from data frame

## Usage

``` r
as.records(x)

# S4 method for class 'data.frame'
as.records(x)
```

## Arguments

- x:

  a `data.frame` with columns representing the slots of records.

## Value

returns a records objects with the columns values in `x`

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
# coerce the records to dataframr
df <- as.data.frame(rcds)
# print the dataframe
print(df)

# coerce the dataframe to records
rcds2 <- as.records(df)
# check the conversion
identical(rcds,rcds2)
} # }
```
