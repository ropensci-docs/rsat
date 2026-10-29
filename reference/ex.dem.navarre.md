# A Digital Elevation Model (DEM) of the region of Navarre (Spain)

Geographically projected `RasterStack` with the digital elevation model
(DEM) of the region of Navarre (Spain). The DEM was obtained from the
[National Center for Geographic
Information](http://centrodedescargas.cnig.es/CentroDescargas/locale?request_locale=en)
of Spain. The DEM is used as a covariate in the Image Mean Anomaly (IMA)
algorithm
([`rsat_smoothing_images`](https://docs.ropensci.org/rsat/reference/rsat_smoothing_images.md)).

## Format

The `RasterStack` contains 6 layers with the same DEM, one for every
image in
[`ex.ndvi.navarre`](https://docs.ropensci.org/rsat/reference/ex.ndvi.navarre.md).

The `RasterStack` coordinates are in the Sinusoidal projection.

- name:

  layer names contain the capturing date of the corresponding image in
  the format "`YYYYJJJ`"

- size:

  113 rows by 105 columns and 6 layers
