# Résultats — Random Forest (cible : CS)

## 1. Run unique (split groupé, seed = 42)

| Métrique | Sans augmentation (`1_raw_data_vegetal`) | Avec augmentation (`1_raw_data_vegetal_augmented`) |
|---|---|---|
| **R² test** | 0.9171 | **0.9271** |
| **MAE test (MPa)** | 1.7630 | **1.6863** |
| **RMSE test (MPa)** | 2.4111 | **2.1521** |
| R² train | 0.9749 | 0.9625 |
| MAE train (MPa) | 0.8940 | 1.2395 |
| RMSE train (MPa) | 1.2524 | 1.5839 |
| Écart R² train − test | 0.058 | 0.036 |

### Hyperparamètres retenus (GridSearchCV, GroupKFold k = 5)

| Hyperparamètre | Sans augmentation | Avec augmentation |
|---|---|---|
| `n_estimators` | 200 | 200 |
| `max_depth` | 10 | 6 |
| `max_features` | 0.7 | 0.5 |
| `min_samples_leaf` | 1 | 4 |
| `min_samples_split` | 2 | 10 |

> Les métriques test et train sont calculées sur les observations réelles uniquement (lignes synthétiques exclues).

---

## 2. Multi-seed (split fixe, seed du modèle variable) — jeu : *[à préciser]*

| Seed | R² train | R² test | MAE test (MPa) | RMSE test (MPa) | Meilleurs hyperparamètres |
|---|---|---|---|---|---|
| 5650 | 0.9778 | 0.9299 | 1.6460 | 2.1101 | depth 8, feat 0.5, leaf 4, split 10, n 300 |
| 7575 | 0.9692 | 0.9230 | 1.7021 | 2.2120 | depth 6, feat 0.7, leaf 4, split 10, n 200 |
| 5059 | — | — | — | — | depth 8, feat 0.5, leaf 4, split 2, n 200 |
| *4ᵉ seed* | — | — | — | — | — |

### Synthèse (moyenne ± écart-type sur 4 seeds)

| Métrique | Valeur |
|---|---|
| **R² test** | **0.9270 ± 0.0030** |
| **MAE test (MPa)** | **1.6709 ± 0.0239** |
| **RMSE test (MPa)** | **2.1541 ± 0.0441** |
| R² train | 0.9734 ± 0.0049 |

---

## 3. Points d'interprétation

- **Augmentation** : léger gain (+0.010 de R² test) et écart train/test plus faible. Le bruit agit comme une régularisation : le GridSearch retient des arbres moins profonds (`max_depth` 6, `min_samples_leaf` 4).
- **Significativité** : sur un seul split, un écart de 0.01 n'est pas conclusif. La variabilité due au découpage (≈ ± 0.01 à 0.03) est du même ordre.
- **Multi-seed** : l'écart-type très faible (± 0.003) reflète uniquement l'aléa interne du Random Forest, le split étant fixe. Il ne mesure pas la variabilité due au découpage train/test.

## 4. À faire

- [ ] Préciser le jeu utilisé pour le multi-seed et le lancer sur l'autre jeu.
- [ ] Refaire le multi-seed en faisant varier le **split** (`GroupShuffleSplit(random_state=seed)`) pour estimer la variance réelle.
- [ ] Comparer sans / avec augmentation en moyenne ± écart-type avant de conclure.
- [ ] Répéter pour la cible **FS** et pour XGBoost / ANN avec le même protocole.
