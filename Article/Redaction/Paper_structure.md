# Paper Structure

## 1. Abstract
- Keywords

## 2. Introduction

## 3. Related Work
- 3.1 ML for predicting the mechanical properties of fibre-reinforced concrete
- 3.2 ANN in cementitious composites (existing studies)
- 3.3 Decision trees vs deep learning on tabular data
- 3.4 Identified gap and hypotheses (expected results)

## 4. Materials and Data Description
Based on sergio work

## 5. Methodology
- 5.1 Preprocessing (mono/bi-fibre merging, encoding, leakage prevention, normalisation)
- 5.2 Exploratory data analysis
- 5.3 Models (ANN / Random Forest / XGBoost)
- 5.4 Training protocol (split, K-fold, GridSearch, hyperparameters, multi-seed repetitions for variance estimation)
- 5.5 Metrics: R², MAE, RMSE
- 5.6 Model interpretation (PFI on all models, PDP on the best model)

### Figures and tables
- Heatmap of the Pearson correlation matrix
- Correlation matrices: mix design parameters vs. measured properties
- Box plots of numerical parameters
- Count plots of categorical parameters
- Table: optimised hyperparameters of each model (5.4)
- Pair plot of numerical parameters (supplementary material)

## 6. Results
- 6.1 CS performance: results and model comparison
- 6.2 FS performance: results and model comparison
- 6.3 Feature importance and partial dependence

### Figures and tables
- Prediction errors on the test set: (a) CS, (b) FS, for each model
- Hold-out comparison through statistical indices (actual vs. predicted regression + summary table)
- 5-fold cross-validation: (a) tabulated results, (b) scores per fold
- Multi-seed variance: R² mean ± SD per model and target (table or box plots)
- Feature importance (PFI) for each model and target
- PDP of the most influential input parameters

## 7. Discussion
- 7.1 ANN vs trees: do the results confirm the literature?
- 7.2 Variance, robustness and statistical significance
- 7.3 Identified limitations (dataset size, non-linearities, robustness of trees to noise…)
- 7.4 Quantitative summary, recommended model per target, improvement directions

## 8. Conclusion

## 9. Data and Code Availability

## 10. References