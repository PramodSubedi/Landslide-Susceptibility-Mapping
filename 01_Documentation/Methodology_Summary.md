# Methodology Summary  
**Landslide Susceptibility Mapping using Frequency Ratio Method**  
**Udayapur District, Eastern Nepal**

## 1. Study Area
Udayapur District, Eastern Nepal.  
Coordinate System: WGS 84 / UTM Zone 45N (EPSG:32645)

## 2. Landslide Inventory
- Total landslides: **211** (field-verified)
- Digitized from high-resolution satellite imagery
- Field verification using GPS
- QA/QC performed
- Split into Training (70%) and Testing (30%) sets

## 3. Conditioning Factors
The following 11 conditioning factors were used (all resampled to 30 m resolution):

| Factor                  | Source / Derivation                  |
|-------------------------|--------------------------------------|
| Elevation               | SRTM DEM                             |
| Slope                   | Derived from DEM                     |
| Aspect                  | Derived from DEM                     |
| Curvature               | Derived from DEM                     |
| TWI (Topographic Wetness Index) | Derived from DEM              |
| Geology / Lithology     | Geological map                       |
| Soil                    | Soil map                             |
| Land Use / Land Cover (LULC) | Remote sensing / existing LULC  |
| Rainfall                | CRU / rainfall data                  |
| Distance to River       | Euclidean distance from river network|
| Distance to Road        | Euclidean distance from road network |


## 4. Method
**Frequency Ratio (FR)** bivariate statistical model.

Frequency Ratio for each class of each factor was calculated as:

\[
FR = \frac{\text{Percentage of landslide pixels in the class}}{\text{Percentage of the class in the study area}}
\]

Landslide Susceptibility Index (LSI) was obtained by summing the FR values of all factors.

## 5. Classification
LSI was classified into **5 classes** using Jenks Natural Breaks:
- Very Low
- Low
- Moderate
- High
- Very High

## 6. Validation
- Method: Receiver Operating Characteristic (ROC) curve
- Metric: Area Under the Curve (AUC) = **0.767**
- Independent testing set (30% of inventory) used for validation

## 7. Software Originally Used
- ArcGIS (ArcMap / ArcGIS Pro)
- Spatial Analyst tools
- Raster Calculator

## 8. Associated Publication
@article{article,
author = {Subedi, Pramod and Joshi, Rajeev and Adhikari, Mandip},
year = {2026},
month = {07},
pages = {},
title = {Landslide Susceptibility Mapping Using GIS-Based Frequency Ratio Method in Eastern Nepal},
volume = {2026},
journal = {Applied and Environmental Soil Science},
doi = {10.1155/aess/6678592}
}