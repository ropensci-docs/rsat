# Extract unique elements

It returns a `records` like `x` but with duplicate elements/rows
removed.

## Usage

``` r
# S4 method for class 'records,ANY'
unique(x)
```

## Arguments

- x:

  a `records` object.

## Value

unique elements in records class

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

duplicate.records <- c(rcds[1],rcds[1])
length(duplicate.records)
print(duplicate.records)
single.record <- unique(duplicate.records)
length(single.record)
print(single.record)
} # }
```
