# Paper Structure

## 1. Abstract
- Keywords

## 2. Introduction

## 3. Related Work
- 3.1 ML for predicting the mechanical properties of fiber-reinforced concrete
- 3.2 ANN in cementitious composites (existing studies)
- 3.3 Decision trees vs deep learning
- 3.4 Identified gap and hypotheses (expected results)

## 4. Materials and Data Description

## 5. Methodology
- 5.1 Preprocessing (mono/bi-fiber merging, encoding, leakage prevention, normalization)
- 5.2 Exploratory data analysis
- 5.3 Models (ANN / Random Forest / XGBoost)
- 5.4 Training protocol (split, K-fold, GridSearch, hyperparameters, multi-seed repetitions for variance estimation)
- 5.5 Metrics: R², MAE, MSE/RMSE

### Graphics
- Pair plot matrix of numerical parameters
- Heatmap of Pearson correlation matrix for the data-points
- Box plots for numerical parameters
- Count plots of categorical parameters
- Optimized hyperparameters of the machine learning models for predicting
- Deux matrices de corrélations entre matériaux / mesures

## 6. Results
- 6.1 CS performance: results and model comparison
- 6.2 FS performance: results and model comparison

### Graphics
- Prediction errors of CS for test data across machine learning algorithms
- Comparison of holdout results obtained from algorithms through statistical indices (linear regression + recap tab)
- Comparison of the machine learning algorithms' performance using 5-fold cross-validation: (a) tabulated results; and (b) graphical representation of the scores for each fold

## 7. Discussion
- 7.1 ANN vs trees: do the results confirm the literature?
- 7.2 Variance, robustness and statistical significance
- 7.3 Identified limitations (small dataset, non-linearities, robustness of trees to noise…)
- 7.4 Quantitative summary, recommended model per target, improvement directions

## 8. Conclusion

## 9. Data and Code Availability

## 10. References

---

## Other Resources
- Feature importance results obtained using the PFI method
- PDP graphs for input parameters
