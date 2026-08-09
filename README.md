# Landslide Susceptibility Mapping – Udayapur District, Eastern Nepal

**GIS | Landslide Susceptibility Mapping | Frequency Ratio (FR) Method | Open Research Project**

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

---

## Overview

This repository contains the complete data, methodology, and results of a landslide susceptibility mapping study conducted in **Udayapur District, Eastern Nepal**, using the GIS-based **Frequency Ratio (FR)** method.

The work was originally performed in ArcGIS and is now organized as an open, reproducible research project.

### Associated Publication

**Subedi, P., Joshi, R., & Adhikari, M. (2026).**  
Landslide Susceptibility Mapping Using GIS-Based Frequency Ratio Method in Eastern Nepal.  
*Applied and Environmental Soil Science*, 2026, Article 6678592.  
https://doi.org/10.1155/aess/6678592

---

## Key Results

| Item                        | Detail                              |
|----------------------------|-------------------------------------|
| Study Area                 | Udayapur District, Eastern Nepal    |
| Landslide Inventory        | 211 field-verified landslides       |
| Method                     | Frequency Ratio (FR)                |
| Model Performance (AUC)    | 0.767                               |
| Classification             | 5 classes (Jenks Natural Breaks)    |
| Resolution                 | 30 m                                |
| Coordinate System          | WGS 84 / UTM Zone 45N (EPSG:32645)  |

---

## Project Structure

```text
Landslide_Susceptibility_Udayapur_FR/
├── 00_README.md
├── LICENSE
├── requirements.txt
├── 01_Documentation/
│   ├── Methodology_Summary.md
│   └── Processing_Notes.md
├── 02_Raw_Data/
│   ├── DEM/
│   ├── Inventory/
│   ├── Study Area/
│   ├── Vector/          # Geology, Soil, River, Road
│   └── Raster/          # (if any original rasters)
├── 03_Processed_Data/
│   ├── Factors_30m/     # All conditioning factors at 30 m
│   ├── FR_Tables/       # Frequency Ratio values
│   └── Inventory/       # Training & Testing splits
├── 04_Results/
│   ├── LSI_Continuous/
│   ├── Classified_5_Classes/
│   └── AUC/
├── 05_Maps_Figures/
│   ├── Factor_maps/
│   └── Final susceptibility maps
├── 06_Python_Notebook/  # Replication notebook
├── 07_ArcGIS_Project/   # Original ArcGIS project (optional)
└── src/                 # Helper Python functions

## Conditioning Factors Used

- Elevation  
- Slope  
- Aspect  
- Curvature  
- Topographic Wetness Index (TWI)  
- Geology  
- Soil  
- Land Use / Land Cover (LULC)  
- Rainfall  
- Distance to River  
- Distance to Road  

All factors were processed at **30 m** resolution.

---

## How to Use This Project

1. Clone or download the repository  
2. Install Python dependencies:

```bash
pip install -r requirements.txt

3. Explore the data:
   - Raw data → `02_Raw_Data/`
   - Processed 30 m factors → `03_Processed_Data/Factors_30m/`
   - Final results → `04_Results/`

4. (Optional) Run the Python replication notebook  
   Open the notebook inside `06_Python_Notebook/` to reproduce the Frequency Ratio workflow using open-source tools.

---

## Citation

If you use this dataset or any part of this project, please cite both the paper and this repository/dataset:

**Paper:**  
Subedi, P., Joshi, R., & Adhikari, M. (2026). Landslide Susceptibility Mapping Using GIS-Based Frequency Ratio Method in Eastern Nepal. *Applied and Environmental Soil Science*, 2026, Article 6678592. https://doi.org/10.1155/aess/6678592

**Dataset / Repository:**  
[Add Zenodo DOI here after upload]

---

## License

This project is released under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.  
You are free to share and adapt the material as long as appropriate credit is given.

See the [LICENSE](LICENSE) file for full details.

---

## Contact

**Pramod Subedi**  
Email: pramod.subedi.np@gmail.com  
Website: https://www.pramods.com.np  
GitHub: https://github.com/PramodSubedi
