# Results

- **LSI_Continuous/** : Continuous Landslide Susceptibility Index raster
- **Classified_5_Classes/** : Final susceptibility map classified into 5 classes using Jenks Natural Breaks
- **FR_Tables/** : Frequency Ratio values recomputed from the training polygons
- **AUC/** : ROC curve and AUC metrics from the testing polygons and background sample
- **RECONCILIATION.md** : Explanation of differences between the published paper results and the corrected open-source notebook

The Python workflow writes `LSI_Continuous/LSI_Continuous.tif`,
`Classified_5_Classes/Classified_5_Classes.tif`, `FR_Tables/FR_tables_python.csv`,
and the ROC plot and metrics under `AUC/`.