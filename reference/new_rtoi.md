# Creates a new `rtoi` object

Creates a new `rtoi` object

## Usage

``` r
new_rtoi(name, region, rtoi_path, db_path, records, size)

# S4 method for class 'character,sf,character,missing,missing,missing'
new_rtoi(name, region, rtoi_path)

# S4 method for class 'character,sf,character,character,missing,missing'
new_rtoi(name, region, rtoi_path, db_path)

# S4 method for class 'character,sf,character,character,records,missing'
new_rtoi(name, region, rtoi_path, db_path, records)

# S4 method for class 'character,sf,character,character,records,numeric'
new_rtoi(name, region, rtoi_path, db_path, records, size)
```

## Arguments

- name:

  the name of the region of interest.

- region:

  an sf object.

- rtoi_path:

  the path to the `rtoi` folder.

- db_path:

  the path to the database.

- records:

  a records object.

- size:

  the size of `rtoi` folder. By default, the size is computed from
  `rtoi_path`.

## Value

the reference of the `rtoi` object
