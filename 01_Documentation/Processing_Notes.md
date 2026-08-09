# Processing Notes

## Data Preparation
- All rasters were resampled / snapped to 30 m resolution matching the DEM.
- Projection: WGS 84 / UTM Zone 45N (EPSG:32645)
- Landslide inventory was converted to points (centroids) for training/testing split where required.
- Euclidean distance rasters were generated for rivers and roads.
- Vector → Raster conversion for Soil and Geology

## Frequency Ratio Calculation
- Training landslides (70%) were used to calculate FR values for each class of every factor.
- FR values were assigned back to the corresponding classes of each factor raster.
- LSI was calculated by summing all weighted factor rasters using Raster Calculator (or equivalent in Python).

## Classification
- Jenks Natural Breaks (Natural Breaks Jenks) was applied to the continuous LSI raster to create 5 susceptibility classes.

## Validation
- Testing landslides (30%) were used to generate the ROC curve and calculate AUC = 0.767.

## Python Replication
- The notebook in `06_Python_Notebook/` aims to fully reproduce the Frequency Ratio workflow using open-source Python libraries (rasterio, geopandas, etc.).
- Source functions are available in `src/fr_functions.py`.

## Known Limitations
- Rainfall data (CRU) has relatively coarse resolution (~50 km).
- Frequency Ratio is a bivariate statistical method and does not account for interactions between factors.