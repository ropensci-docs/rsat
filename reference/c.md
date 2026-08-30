# Combine values into a vector or a list

This is a generic function which combines its arguments.

## Usage

``` r
# S4 method for class 'extent_crs'
c(x, ...)

# S4 method for class 'records'
c(x, ...)
```

## Arguments

- x:

  a `records` object.

- ...:

  additional arguments.

## Value

a combination of 'x' class elements

## Details

The default method combines its arguments to form a vector. All
arguments are coerced to a common type which is the type of the returned
value. All attributes except names are removed.
