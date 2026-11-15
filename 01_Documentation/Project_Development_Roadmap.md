# Project Development Roadmap

**Landslide Susceptibility Mapping – Udayapur District, Eastern Nepal**

This document tracks the development history of the project, showing what was delivered in Version 1, what is added in Version 2, and what is planned for future additions.

---

## Version 1: Initial Release

### What Was Delivered

**Core Components:**
- Complete landslide susceptibility mapping workflow using Frequency Ratio (FR) method
- Study area: Udayapur District, Eastern Nepal
- Coordinate System: WGS 84 / UTM Zone 45N (EPSG:32645)
- Resolution: 30 m
- Conditioning factors: 11 (Elevation, Slope, Aspect, Curvature, TWI, Geology, Soil, LULC, Rainfall, Distance to River, Distance to Road)

**Data:**
- Digital Elevation Model (DEM): SRTM, 30 m
- Landslide Inventory: 211 field-verified landslides (208 after cleaning)
- Training/Test split: 70% training / 30% testing
- Vector layers: Geology, Soil, River, Road
- Frequency Ratio tables calculated from training landslides

**Results:**
- Continuous Landslide Susceptibility Index (LSI) raster
- Classified susceptibility map (5 classes using Jenks Natural Breaks)
- AUC = 0.767 (published paper) / AUC = 0.822 (corrected open-source notebook)

**Documentation:**
- Methodology summary
- Processing notes
- Data sources and dictionary
- README with project overview
- Citation files (CITATION.cff)
- CV summary
- Quick start guide

**Code:**
- Python notebook for Frequency Ratio replication
- Helper functions in `src/`
- Pinned dependencies in `requirements.txt`

**Licensing:**
- Code: MIT License
- Data & documentation: CC BY 4.0

---

## Version 2: Current Enhancements

### What Is Added in Version 2

**Notebook Improvements:**
- Version 2 notebook: `02_Frequency_Ratio_Replication_Stepwise.ipynb` (step-wise format)
- Exact class breaks from FR calculation.xlsx Sheet1 enforced
- Training polygons: 146 polygons (EPSG:4326), Testing polygons: 62 polygons (EPSG:4326)
- Train/test split confirmed: 70.2% / 29.8% (matches paper design)
- Polygon reprojection to EPSG:32645 implemented
- Pixel count disclosure: ~1,210 landslide pixels from provided polygons vs ~10,768 in published FR tables
- AUC discrepancy documentation: Results may differ from published 0.767 due to pixel count difference
- Version 2 summary with pixel count metrics

**Documentation Enhancements:**
- Main README.md completely rewritten with:
  - DOI and license badges
  - Key results table (including AUC 0.767/0.822)
  - Quick links section
  - Project structure diagram
  - Conditioning factors list
  - Reproducibility steps with expected runtime (~2 hours)
  - Validation note comparing paper vs corrected notebook results
  - BibTeX citation
  - License details
  - Contact information
- Data Sources and Dictionary document created (`01_Documentation/Data_Sources_and_Dictionary.md`)
- Folder-level README files created for:
  - 02_Raw_Data/
  - 02_Raw_Data/Inventory/
  - 02_Raw_Data/Vector/
  - 03_Processed_Data/
  - 03_Processed_Data/Factors_30m/
  - 03_Processed_Data/FR_Tables/
  - 04_Results/
- CITATION.cff updated to cff-version 1.2.0 with proper author structure
- CV_SUMMARY.md updated with key achievements and technical stack
- QUICK_START.md updated with adaptability guide for other study areas
- Project Development Roadmap created (this document)

**Reproducibility Improvements:**
- Fixed random seed (42) documented
- Dependency versions pinned in requirements.txt
- Notebook executable via nbconvert --execute
- Python version specified (3.9+, verified with 3.10.9)
- Version tagged v1.0.0 on GitHub

---

## Future Addition Plan

### Short-Term (Version 2.1)

**Notebook Enhancements:**
- Complete FR calculation implementation from raw rasters (when available)
- Complete Jenks Natural Breaks classification implementation
- Complete ROC/AUC validation with background points
- Complete LSI raster saving functionality
- Add error handling for missing input files
- Add progress indicators for long-running cells

**Documentation:**
- QUICK_START.md: Add study-area adaptation examples
- Data_Sources_and_Dictionary.md: Complete missing agency/year/scale information for Geology, Soil, and LULC layers
- RECONCILIATION.md: Detailed explanation of AUC differences (0.767 vs 0.822)

**Code:**
- Refactor notebook cells into reusable Python functions
- Add unit tests for FR calculation
- Add CLI interface for notebook execution

### Medium-Term (Version 2.2)

**Methodology Improvements:**
- Implement area-based Frequency Ratio using polygon rasterisation onto 30m grid
- Document pixel counting rule (centroid vs intersection)
- Add option for buffered landslide pixels (to match published ~10,768 count)
- Add sensitivity analysis for different cell-counting rules

**Results:**
- Generate LSI continuous raster from reclassified factor rasters
- Generate classified 5-class map
- Generate ROC curve figure
- Save all outputs to 04_Results/

**Validation:**
- Compare AUC results with published paper (0.767)
- Document any differences and reasons
- Cross-validate with independent test set

### Long-Term (Version 3.0)

**Study Area Adaptation:**
- Make notebook fully parameterizable for other study areas
- Add configuration file (YAML/JSON) for study area settings
- Add template for input data preparation
- Document data requirements for new study areas

**Methodology Extensions:**
- Add alternative statistical methods (Weights of Evidence, Logistic Regression, Analytic Hierarchy Process)
- Add ensemble methods
- Add machine learning comparison (Random Forest, SVM, Neural Networks)

**Outputs:**
- Interactive web map of susceptibility results
- Export to GIS formats (GeoPackage, GeoTIFF)
- Add uncertainty analysis
- Add change detection capability (multi-temporal)

**Documentation:**
- Complete user manual
- API documentation for helper functions
- Tutorial for adapting to other regions
- Case studies from other districts

**Community:**
- Zenodo DOI creation
- Citation in additional publications
- Community contributions via GitHub issues/pull requests

---

## Development Timeline

| Version | Status | Key Features | Target Date |
|---------|--------|--------------|-------------|
| v1.0.0 | ✅ Released | Initial FR workflow, basic notebook, documentation | Completed |
| v2.0 | ✅ Released | Version 2 notebook, class breaks, pixel count disclosure, updated documentation | Completed |
| v2.1 | 🔄 In Progress | Complete FR calculation, Jenks classification, ROC/AUC | TBD |
| v2.2 | 📋 Planned | Area-based FR from polygons, sensitivity analysis | TBD |
| v3.0 | 📋 Planned | Multi-method comparison, other study area adaptation | TBD |

---

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

Please read the CONTRIBUTING guidelines (to be added) before submitting.

---

## Contact

**Pramod Subedi**  
Email: pramod.subedi.np@gmail.com  
Website: https://www.pramods.com.np  
GitHub: https://github.com/PramodSubedi  

**Associated Publication:**  
Subedi, P., Devkota, U., Adhikari, S., Baral, D., Adhikari, M., & Joshi, R. (2026).  
Landslide Susceptibility Mapping Using GIS-Based Frequency Ratio Method in Eastern Nepal.  
*Applied and Environmental Soil Science*, 2026, Article 6678592.  
https://doi.org/10.1155/aess/6678592