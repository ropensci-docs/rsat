# Renames an `rtoi`

Renames all parameters and folder name of an `rtoi`.

## Usage

``` r
rename(x, newname)

# S4 method for class 'rtoi,character'
rename(x, newname)
```

## Arguments

- x:

  an rtoi object

- newname:

  a character class to rename the `rtoi`.

## Value

nothing. the changes the internal name of the rtoi

## Examples

``` r
if (FALSE) { # \dontrun{
myrtoi <- read_rtoi("file_path/rtoir_name")
rename(myrtoi, "Navarre_BACK")
} # }
```
