# Data Sources and Dictionary

**Landslide Susceptibility Mapping – Udayapur District, Eastern Nepal**

This document describes all datasets used in the study, their sources, processing steps, and class definitions.

## Coordinate System & Resolution

- **CRS**: WGS 84 / UTM Zone 45N (EPSG:32645)
- **Resolution**: 30 m (all rasters snapped and resampled to match the DEM)

---

## 1. Landslide Inventory

| Item                    | Detail                                      |
|-------------------------|---------------------------------------------|
| Original count          | 211 field-verified landslides               |
| Format                  | Point shapefile + KMZ                       |
| Source                  | High-resolution satellite imagery + field GPS verification |
| Split                   | 70% training / 30% testing                  |
| Location                | `02_Raw_Data/Inventory/` and `03_Processed_Data/Inventory/` |

---

## 2. Digital Elevation Model (DEM)

| Item           | Detail                          |
|----------------|---------------------------------|
| Source         | SRTM                            |
| Resolution     | 30 m                            |
| Derived factors| Elevation, Slope, Aspect, Curvature, TWI |

---

## 3. Conditioning Factors

### Topographic Factors (derived from DEM)
- **Elevation**
- **Slope** (degrees)
- **Aspect**
- **Curvature** (plan/profile or combined)
- **Topographic Wetness Index (TWI)**

### Categorical / Thematic Factors

| Factor              | Source / Notes                              | Original Format |
|---------------------|---------------------------------------------|-----------------|
| Geology / Lithology | Geological map of the area                  | Vector (shapefile) |
| Soil                | Soil map                                    | Vector (shapefile) |
| Land Use / Land Cover (LULC) | Remote sensing / existing LULC product | Raster or Vector |
| Rainfall            | CRU data (coarse resolution ~50 km)         | Raster          |
| Distance to River   | Euclidean distance from river network       | Derived         |
| Distance to Road    | Euclidean distance from road network        | Derived         |

> **Note**: Exact agency, year, and scale of the Geology, Soil, and LULC layers should be completed by the author for full transparency.

---

## 4. Frequency Ratio Tables

FR values for every class of every factor are stored in:

`03_Processed_Data/FR_Tables/`

These tables were calculated using the 70% training landslides.

---

## 5. Known Limitations of Input Data

- Rainfall data (CRU) has relatively coarse spatial resolution (~50 km).
- Some thematic layers (geology, soil, LULC) may have original scales coarser than 30 m.