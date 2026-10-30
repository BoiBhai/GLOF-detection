# GLOF susceptibility and monitoring prototype — run report

**Generated:** 2026-10-29T18:34:18+05:30

## Data loaded
- Kashmir susceptibility layer: 155 rows; CRS `EPSG:32643`.
- Susceptibility class field: `sus_class`.
- Continuous score field: `None`.
- Area layer available: yes.
- Historical event inventory raw rows: not available.
- Event inventory rows with usable year: not available.
- Event year range under the 2025 cutoff: NA–NA.
- Event inventory rows without a usable year under the 2025 cutoff: not available.

## Statistical lake-dynamics results
- Valid paired lake records: 155.
- Median percentage area change: 0.0%.
- Mean percentage area change: 4.44%.
- Bootstrap 95% interval for median percentage change: [0.0, 0.0]%.
- Paired Wilcoxon test p-value: 0.00021.
- Area units: as encoded in the source dataset; verify before reporting.

## Susceptibility ML validation

- Task: High/Very-high susceptibility versus other classes.
- Observations / predictors: 155 / 24.
- Validation: grouped spatial cross-validation with 5 geographic clusters.
- Best model by mean spatial-fold balanced accuracy: Random Forest.
- Best-model pooled out-of-fold balanced accuracy: 0.983.
- Best-model pooled out-of-fold macro-F1: 0.983.
- **Interpretation limit:** metrics measure reproduction of susceptibility classes / score-derived classes, not prediction of observed future GLOFs.

### Spatial-fold model table

| Model | Mean balanced accuracy | SD | Mean macro-F1 | Folds |
|---|---:|---:|---:|---:|
| Random Forest | 0.986 | 0.021 | 0.985 | 5 |
| Logistic Regression | 0.965 | 0.041 | 0.945 | 5 |
| Dummy baseline | 0.5 | 0.0 | 0.421 | 5 |

## Satellite case study

Live Sentinel-2 processing did not complete: `ModuleNotFoundError("No module named 'planetary_computer'")`. Consult the official ISRO/NRSC study for the reference scene analysis.

## Literature reference findings (not computed by this notebook)
- ISRO/NRSC reported approximately 105 ha drained from South Lhonak Lake between the 28 September and 4 October 2023 satellite views.
- A 2025 South Lhonak study reported lake expansion from approximately 1.12 km² (2016) to 1.63 km² (2023), about 45.5%, using its own remote-sensing workflow.
- The 2026 Kashmir Himalaya study reports 155 lakes, with 5 very-high / 35 high / 77 moderate / 32 low / 6 very-low susceptibility classes and AHP consistency ratio 0.07. These are published results from that study, not calculations made here.

## Decision-relevant limitations
1. A susceptibility class is not an event probability or forecast date.
2. Small sample, regional restriction, expert-label uncertainty and possible spatial dependence limit generalisation.
3. Historical event inventories are incomplete and largely positive-only; the notebook does not claim independent event-prediction sensitivity/specificity.
4. The optical mask is not manually validated; SCL and NDWI thresholds can misclassify shadow, snow/ice, sediment and narrow water channels.
5. For a true forecasting study, construct a lake-year panel and evaluate held-out future periods and held-out regions using PR-AUC, recall at an operational alert budget, calibration/Brier score, event lead time, and false alarms per lake-year.

## Outputs
The notebook writes reproducible tables and figures to `glof_project/outputs/` where the corresponding analysis completed.