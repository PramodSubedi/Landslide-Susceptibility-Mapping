# Landslide Susceptibility Mapping – Udayapur District, Eastern Nepal

[![DOI](https://img.shields.io/badge/DOI-10.1155%2Faess%2F6678592-blue)](https://doi.org/10.1155/aess/6678592)
[![License: MIT](https://img.shields.io/badge/Code-MIT-green.svg)](LICENSE)
[![License: CC BY 4.0](https://img.shields.io/badge/Data-CC%20BY%204.0-lightgrey.svg)](NOTICE)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)

**GIS-based Frequency Ratio landslide susceptibility mapping of Udayapur District, Eastern Nepal**
Complete open data, methodology, results, and reproducible Python workflow.

> Associated publication:
> Subedi, P., Devkota, U., Adhikari, S., Baral, D., Adhikari, M., & Joshi, R. (2026).
> Landslide Susceptibility Mapping Using GIS-Based Frequency Ratio Method in Eastern Nepal.
> Applied and Environmental Soil Science, 2026, Article 6678592.
> https://doi.org/10.1155/aess/6678592

---

## Key Results

| Item                       | Value                                      |
|----------------------------|--------------------------------------------|
| Study Area                 | Udayapur District, Eastern Nepal           |
| Landslide Inventory        | 211 field-verified                         |
| Method                     | Frequency Ratio (FR)                       |
| Model Performance (AUC)    | 0.767                                      |
| Classification             | 5 classes (Jenks Natural Breaks)           |
| Resolution                 | 30 m                                       |
| Coordinate System          | WGS 84 / UTM Zone 45N (EPSG:32645)         |
| Conditioning Factors       | 11                                         |

---

## Quick Links

- **Paper**: [DOI 10.1155/aess/6678592](https://doi.org/10.1155/aess/6678592)
- **Reproduce the analysis**: [QUICK_START.md](QUICK_START.md)
- **Methodology**: [01_Documentation/Methodology_Summary.md](01_Documentation/Methodology_Summary.md)
- **Data Sources & Dictionary**: [01_Documentation/Data_Sources_and_Dictionary.md](01_Documentation/Data_Sources_and_Dictionary.md)
- **Final Maps**: [05_Maps_Figures](05_Maps_Figures)
- **Python Notebook**: [06_Python_Notebook](06_Python_Notebook)

---

## Project Structure

```text
Landslide-Susceptibility-Mapping/
├── 01_Documentation/          # Methodology, processing notes, data dictionary
├── 02_Raw_Data/               # Original DEM, inventory, geology, soil, rivers, roads
├── 03_Processed_Data/         # 30 m factors, FR tables, train/test splits
├── 04_Results/                # Continuous LSI, 5-class map, AUC, reconciliation
├── 05_Maps_Figures/           # All publication-ready figures
├── 06_Python_Notebook/        # Fully reproducible Frequency Ratio notebook
├── src/                       # Helper functions
├── LICENSE                    # MIT (code)
├── NOTICE                     # CC BY 4.0 (data & documentation)
├── requirements.txt
├── QUICK_START.md
└── CITATION.cff
```

---

## Conditioning Factors

Elevation • Slope • Aspect • Curvature • Topographic Wetness Index (TWI) • Geology • Soil • Land Use / Land Cover (LULC) • Rainfall • Distance to River • Distance to Road

All factors processed at **30 m** resolution.

---

## How to Reproduce

1. Clone the repository
2. Create a virtual environment and install dependencies (`pip install -r requirements.txt`)
3. Follow the instructions in [QUICK_START.md](QUICK_START.md)

The notebook fully reproduces the Frequency Ratio workflow using open-source Python libraries (rasterio, geopandas, etc.).

**Expected runtime**: ~2 hours
**Python version**: 3.9+ (verified with 3.10.9)

---

## Validation Note

- **Published paper**: 211 landslides, AUC = 0.767
- **Corrected open-source notebook**: 208 landslides (after data cleaning), AUC = 0.822

Both results are valid. See [04_Results/RECONCILIATION.md](04_Results/RECONCILIATION.md) for details.

---

## Citation

**Paper**
```bibtex
@article{Subedi2026,
  author  = {Subedi, Pramod and Devkota, Utpal and Adhikari, Saraswoti and Baral, Deepa and Adhikari, Mandip and Joshi, Rajeev},
  title   = {Landslide Susceptibility Mapping Using GIS-Based Frequency Ratio Method in Eastern Nepal},
  journal = {Applied and Environmental Soil Science},
  year    = {2026},
  volume  = {2026},
  pages   = {6678592},
  doi     = {10.1155/aess/6678592}
}
```

**Dataset / Repository** (update with Zenodo DOI once available)
Subedi, P. (2026). Landslide Susceptibility Mapping – Udayapur District, Eastern Nepal (v1.0.0). GitHub. https://github.com/PramodSubedi/Landslide-Susceptibility-Mapping

---

## License

- **Code** (notebooks, `src/`): [MIT License](LICENSE)
- **Data and documentation**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](NOTICE)

---

## Contact

**Pramod Subedi**
Email: pramod.subedi.np@gmail.com
Website: https://www.pramods.com.np
GitHub: https://github.com/PramodSubedi
