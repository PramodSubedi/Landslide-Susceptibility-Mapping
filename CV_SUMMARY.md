# Landslide Susceptibility Mapping - Udayapur District
## Open-Research Project | Frequency Ratio Method

**Pramod Subedi** | GitHub: @PramodSubedi | DOI: zenodo.org/XXXXXX (pending)

---

### Project Overview
Reproducible GIS research implementing a **Frequency Ratio (FR) landslide susceptibility mapping** workflow using open-source Python tools. Originally performed in ArcGIS, now fully replicated in Python with pinned dependencies and documented methodology.

**Key Metrics:**
- **Landslides:** 211 field-verified (original) / 208 points (corrected)
- **AUC:** 0.767 (published paper) / 0.822 (corrected notebook)
- **Study Area:** Udayapur District, Eastern Nepal
- **Resolution:** 30 m
- **Classes:** 5 (Jenks Natural Breaks)
- **Coordinate System:** WGS 84 / UTM Zone 45N (EPSG:32645)

---

### Methodology
- **11 Conditioning Factors:** Elevation, Slope, Aspect, Curvature, TWI, Geology, Soil, LULC, Rainfall, Distance to River, Distance to Road
- **Statistical Method:** Frequency Ratio (FR) bivariate analysis
- **Classification:** Jenks Natural Breaks optimization
- **Validation:** ROC curve with AUC metric
- **Train/Test Split:** 70% training / 30% independent testing

**Tools:** Python 3.10.9, rasterio, geopandas, numpy, pandas, scikit-learn, matplotlib, seaborn, jenkspy, shapely, fiona, pyproj, contextily

---

### Reproducibility
- ✅ Pinned dependency versions (`requirements.txt`)
- ✅ Python version specified (3.9+, verified with 3.10.9)
- ✅ Notebook executable via `nbconvert --execute`
- ✅ Fixed seed option (`random.seed(42)`)
- ✅ Version tagged `v1.0.0` on GitHub
- ✅ Zenodo DOI in progress (GitHub Zenodo integration)

**Estimated time for full reproduction:** ~2 hours

---

### Licensing
- **Code & software:** MIT License (see `LICENSE`)
- **Data & documentation:** CC BY 4.0 (see `NOTICE`)

**Citation:**
```
Subedi, P., Devkota, U., Adhikari, S., Baral, D., Adhikari, M., & Joshi, R. (2026). 
Landslide Susceptibility Mapping Using GIS-Based Frequency Ratio Method in Eastern Nepal. 
Applied and Environmental Soil Science, 6678592. 
https://doi.org/10.1155/aess/6678592
```

---

### Zenodo DOI
This repository is versioned as `v1.0.0` and connected to Zenodo via GitHub integration. A citable DOI will be automatically generated upon tag push, making this work officially citable in research publications.

**Pending DOI:** `10.5281/zenodo.XXXXXX` (to be replaced with actual DOI)

---

### Contact
**Pramod Subedi**  
Email: pramod.subedi.np@gmail.com  
GitHub: https://github.com/PramodSubedi  
Website: https://www.pramods.com.np

---

### Quick Links
- **GitHub:** https://github.com/PramodSubedi/Landslide-Susceptibility-Mapping
- **Repository:** Fully open with documentation, code, and data
- **Results:** `04_Results/` folder with LSI rasters and AUC metrics
- **Notebook:** `06_Python_Notebook/` - fully reproducible Frequency Ratio workflow