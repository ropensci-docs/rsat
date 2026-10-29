# Extract or replace parts of an object

Operators acting on vectors, matrices, arrays and lists to extract or
replace parts.

## Usage

``` r
# S4 method for class 'extent_crs,ANY,ANY,ANY'
x[i]

# S4 method for class 'extent_crs,ANY,ANY,ANY'
x[i] <- value

# S4 method for class 'records,ANY,ANY,ANY'
x[i]

# S4 method for class 'records,ANY,ANY,ANY'
x[i] <- value
```

## Arguments

- x:

  object from which to extract element(s) or in which to replace
  element(s).

- i:

  numeric argument. The the position of the element to select/modify.

- value:

  a `records` argument. The slot of the records to be changed.

## Value

returns a selected value
