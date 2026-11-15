# Quick-Start Guide: Landslide Susceptibility Mapping

## Overview
This guide reproduces the Frequency Ratio (FR) landslide susceptibility mapping workflow from the published paper in Udayapur District, Eastern Nepal.

**Time required:** ~2 hours  
**Python version:** 3.9+ (verified with 3.10.9)  
**Reproducibility:** Fully reproducible with pinned dependencies

---

## Step 1: Setup

```bash
# 1. Clone the repository
git clone https://github.com/PramodSubedi/Landslide-Susceptibility-Mapping.git

# 2. Enter project directory
cd Landslide-Susceptibility-Mapping

# 3. Create and activate a virtual environment
python -m venv .venv
# Windows:
.\.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

# 4. Install pinned dependencies
pip install -r requirements.txt
```

---

## Step 2: Run the Replication Notebook

```bash
# Execute the notebook top-to-bottom with a fixed seed for reproducibility
python -c "import random; random.seed(42)" && \
jupyter nbconvert --to notebook --execute \
  --ExecutePreprocessor.timeout=120 \
  06_Python_Notebook/*.ipynb
```

**Alternative (without pre-set seed):**
```bash
jupyter nbconvert --to notebook --execute \
  --ExecutePreprocessor.timeout=120 \
  06_Python_Notebook/*.ipynb
```

---

## Step 3: Verify Results

Check that the notebook ran successfully by examining:

```bash
# Results directory structure
ls -la 04_Results/
# Should contain: LSI_Continuous/, Classified_5_Classes/, AUC/

# AUC values reported in the notebook
# Original paper: AUC = 0.767
# Corrected notebook: AUC = 0.822
```

---

## Step 4: Cite the Work

**Paper citation:**
```
Subedi, P., Joshi, R., & Adhikari, M. (2026). 
Landslide Susceptibility Mapping Using GIS-Based Frequency Ratio Method in Eastern Nepal. 
Applied and Environmental Soil Science, 2026, Article 6678592. 
https://doi.org/10.1155/aess/6678592
```

**Repository citation (once Zenodo DOI is active):**
```
Subedi, P. (2026). Landslide Susceptibility Mapping – Udayapur District, Eastern Nepal (v1.0.0). 
GitHub. https://github.com/PramodSubedi/Landslide-Susceptibility-Mapping.
```

---

## Expected Output

After running the notebook, you should have:

| Output | Location | Description |
|--------|----------|-------------|
| LSI Continuous Raster | `04_Results/LSI_Continuous/` | Continuous susceptibility index |
| Classified Map (5 classes) | `04_Results/Classified_5_Classes/` | 5-class susceptibility map |
| AUC metrics | `04_Results/AUC/` | ROC curve and AUC value |

**Landslide count:** 211 (original) or 208 (after data cleaning)  
**Study area:** Udayapur District, Eastern Nepal  
**Coordinate system:** WGS 84 / UTM Zone 45N (EPSG:32645)  
**Resolution:** 30 m

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| `ModuleNotFoundError` | Ensure `pip install -r requirements.txt` completed successfully |
| Notebook timeout | Increase `--ExecutePreprocessor.timeout` value (max 300 seconds) |
| Memory error | Close other applications; the process requires ~2GB RAM |
| AUC mismatch with paper | Verify you're using Python 3.10.9 and the pinned `requirements.txt` |

---

## Reproducibility Checklist

- [ ] `requirements.txt` installed with pinned versions
- [ ] Python 3.9+ version confirmed
- [ ] Seed set to 42 (or your chosen value)
- [ ] Notebook executed with `nbconvert --execute`
- [ ] Results compared to: AUC 0.767 (paper) / 0.822 (corrected notebook)
- [ ] Landslide count: 211 (original) or 208 (cleaned)

---

**This project is released under the MIT license for code and CC BY 4.0 for data.**  
**Zenodo DOI:** Will be generated upon tag push to GitHub (v1.0.0 already pushed).