# Testing function

Function used for testing some internal functions in continuous
integration.

## Usage

``` r
test_function()
```

## Examples

``` r
test_function()
#> File md5:8EB3193CB459098D9736B1AF4BE179C5
#> Oficial md5:8eb3193cb459098d9736b1af4be179c5
#> Return TRUE
#> File md5:8EB3193CB459098D9736B1AF4BE179C5
#> Oficial md5:8eb3193cb459098d9736b1af4be179c51
#> Return FALSE
#> Extent: 
#>  EPSG: NA
#>  xmin: NA
#>  ymin: NA
#>  xmax: NA
#>  ymax: NA
#> Warning: GDAL Error 1: PROJ: proj_create_from_database: crs not found
#> Extent: 
#>  EPSG:  NA 
#>  xmin:  2 
#>  ymin:  1 
#>  xmax:  1 
#>  ymax:  1 
#> Search query: https://cmr.earthdata.nasa.gov/search/granules?short_name=&point=2,1&equator_crossing_date=2021-11-01T10:00:00Z,2021-11-01T12:00:00Z&page_size=2000
#> Search query: https://cmr.earthdata.nasa.gov/search/granules?short_name=&bounding_box=1,1,1,1&equator_crossing_date=2021-11-01T10:00:00Z,2021-11-01T12:00:00Z&page_size=2000
#> Search query: https://cmr.earthdata.nasa.gov/search/granules?short_name=&bounding_box=1,1,1,1&equator_crossing_date=2021-11-01T10:00:00Z,2021-11-01T12:00:00Z&page_size=2000
#> Search query: https://cmr.earthdata.nasa.gov/search/granules?short_name=&bounding_box=-2.49908963576402,41.9095732069108,-0.726158447400539,43.3146327061922&equator_crossing_date=2021-11-01T10:00:00Z,2021-11-01T12:00:00Z&page_size=2000
#> Record: 
#> sat: character
#> name: character
#> date: 2021-11-01
#> product: character
#> path: 2
#> row: 1
#> tileid: 
#> download: character
#> file_path: character
#> preview: character
#> api_name: 
#> order: FALSE
```
