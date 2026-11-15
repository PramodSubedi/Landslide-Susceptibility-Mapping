# Conditioning Factors (30 m)

This folder contains raster layers for 10 of the 11 conditioning factors used in
the Frequency Ratio model. Road distance is generated from
`02_Raw_Data/Vector/Road.shp` by the Python workflow.

The source layers use approximately 30 m cells in EPSG:32645. During analysis,
they are aligned to the elevation grid; small differences in raster dimensions
and cell size are handled by nearest-neighbor resampling.