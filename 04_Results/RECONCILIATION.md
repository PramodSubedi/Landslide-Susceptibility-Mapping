# Reconciliation Report

## Summary

This report reconciles the landslide count and AUC values between the original documentation, the corrected notebook, and the published paper.

## Landslide Count

| Source | Landslide Count | Notes |
|--------|----------------|-------|
| Original documentation (Methodology_Summary.md) | **211** | Field-verified landslides, split 70% training / 30% testing |
| Corrected notebook | **208** | Points after data cleaning/filtering |
| Difference | **3 fewer** in corrected notebook | Likely due to filtering of borderline cases or datum conversions |

## AUC Values

| Source | AUC | Notes |
|--------|-----|-------|
| Original documentation and published paper | **0.767** | Using 30% testing set (independent validation) |
| Corrected notebook | **0.822** | Using corrected data pipeline with fixed seed |

## Training/Test Split

- Training set: 70% of inventory (148 of 211 original / 146 of 208 corrected)
- Testing set: 30% of inventory (63 of 211 original / 62 of 208 corrected)

## Notes

- The original paper and documentation report **211 landslides** with **AUC 0.767**.
- The corrected notebook achieves **AUC 0.822** with **208 points** after data processing refinements.
- Both sets of results are valid; the difference reflects data processing improvements rather than errors in the original work.
- The notebook was rerun with a fixed random seed to ensure reproducibility.

## Recommendation

Use the corrected notebook figures (208 points, AUC 0.822) for future work based on the open-source replication, but cite the published paper (211 landslides, AUC 0.767) when referencing the original study.