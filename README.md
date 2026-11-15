# Landslide Susceptibility Mapping – Udayapur District, Eastern Nepal

**GIS | Landslide Susceptibility Mapping | Frequency Ratio (FR) Method | Open Research Project**

[![License: MIT](https://img.shields.io/badge/License-MIT-lightgrey.svg)](https://opensource.org/licenses/MIT)

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
Landslide_Susceptibility_Mapping/
├── README.md
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
└── src/                 # Helper Python functions
```

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

## What the AUC Measures

The Area Under the Curve (AUC) of the Receiver Operating Characteristic (ROC) curve measures the model's ability to distinguish between landslide and non-landslide areas:

- **AUC = 1.0**: Perfect classification - the model perfectly separates landslides from non-landslides.
- **AUC = 0.5**: No discrimination - the model performs no better than random chance.
- **AUC range**: Typically between 0.5 and 1.0 for useful models.

In this project, AUC = 0.767 (original) / 0.822 (corrected notebook) indicates good but not excellent discriminative power. The model ranks a randomly selected landslide pixel higher than a randomly selected non-landslide pixel about 76.7% / 82.2% of the time.

**Interpretation guidelines:**
- 0.9-1.0: Excellent
- 0.8-0.9: Good
- 0.7-0.8: Acceptable
- 0.6-0.7: Poor
- 0.5-0.6: Fail

## Limitations

- Rainfall data (CRU) has relatively coarse resolution (~50 km), which may not capture local rainfall-triggered landslides.
- Frequency Ratio is a bivariate statistical method and does not account for interactions between conditioning factors.
- The model was developed for Udayapur District; applicability to other regions with different geomorphological settings should be validated.
- 3 landslides were excluded during data cleaning, reducing the count from 211 to 208 points AUC 0.822.
- The 5-class Jenks Natural Breaks classification uses Jenks optimization which can be sensitive to outlier values.
- AUC values are dependent on the train/test split; different splits may yield different performance.

## How to Use This Project

1. Clone or download the repository
3. Ensure Python 3.9+ is being used (this project was verified with Python 3.10.9)

4. (Optional) Run the notebook top-to-bottom using nbconvert:

```bash
jupyter nbconvert --to notebook --execute --inplace 06_Python_Notebook/*.ipynb
```

Or with a fixed seed:

```bash
python -c "import random; random.seed(42)" && jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=120 06_Python_Notebook/*.ipynb
```

5. Explore the data:  
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
Subedi, P., Joshi, R., & Adhikari, M. (2026).
Landslide Susceptibility Mapping Using GIS-Based Frequency Ratio Method in Eastern Nepal.
*Applied and Environmental Soil Science*, 2026, Article 6678592.
https://doi.org/10.1155/aess/6678592


---

## License

This project uses a dual-license approach:
- **Code and software** (Python notebooks, scripts, and helper functions in `src/`) are released under the **MIT license** (see [LICENSE](LICENSE) file).
- **Data and documentation** (raw inventory files, processed conditioning factors, maps, and this README) are released under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.  
You are free to share and adapt the material as long as appropriate credit is given.

See the [LICENSE](LICENSE) file for full details.

## Zenodo DOI

This project is versioned as `v1.0.0` and can be made citable via Zenodo.

**To create a Zenodo DOI:**

1. Go to https://github.com/PramodSubedi/Landslide-Susceptibility-Mapping/settings/integrations
2. Click "Connect to Zenodo" and authenticate your GitHub account
3. Configure the integration:
   - Repository: `PramodSubedi/Landslide-Susceptibility-Mapping`
   - Trigger: "Create a new version on each Git tag push"
4. Zenodo will automatically process the `v1.0.0` tag (already pushed to GitHub)
5. A DOI will be generated and displayed on the repository page
6. The DOI will appear at https://doi.org/XXXXXX

**Your citation-ready reference:**

```
Subedi, P. (2026). Landslide Susceptibility Mapping – Udayapur District, Eastern Nepal (v1.0.0). GitHub. https://github.com/PramodSubedi/Landslide-Susceptibility-Mapping. doi: 10.5281/zenodo.XXXXXX
```

Replace `10.5281/zenodo.XXXXXX` with the actual DOI once Zenodo processes it (typically within 5-10 minutes of tag push).

This DOI will make your repository officially citable in research papers—a valuable asset for master's research assistantship applications.

---

## Contact

**Pramod Subedi**  
Email: pramod.subedi.np@gmail.com  
Website: https://www.pramods.com.np  
GitHub: https://github.com/PramodSubedi
