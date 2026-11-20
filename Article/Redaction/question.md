### 1. Incohérence dans les données

1. Fibres synthétiques (ch.antif. et ch.strux)
Je pense les retirer : leur teneur en air vaut 0 partout (non mesurée) et leur masse volumique est la même partout (2 245,5, la valeur du mortier sans fibre). Ça fausserait le modèle, surtout que l’air et la densité font partie des variables les plus influentes. De plus, l’étude porte sur les fibres végétales uniquement ? On peut le tourner comme ça ? 

<!-- 2. Lin 6 en monofibre
Aux dosages 1,2 , 2 et 4 kg/m³, les 12 lignes ont exactement les mêmes résistances (FS = 4,66 MPa, CS = 26,75 MPa) à tous les âges (1, 7, 28 et 90 jours). C’est impossible physiquement (selon ce que j'ai lu), ça ressemble à des valeurs recopiées, qui fausseraient l’entraînement. On a les vraies valeurs ? Sinon, je les retire. -->

<!-- 3. Bifibres : jour 1 = jour 7
Pour 8 formulations bifibres, les FS et CS à 1 jour sont strictement identiques à ceux à 7 jours. Normal ?  -->

Exemple : 
chanvre 5	bambou 15	Days	FS	    CS
0,6	        2,6	        1	    5,88    22,46
0,6	        2,6	        7	    5,88    22,46

### GrassHopper (logiciel méta méteriaux)

> Voir les types modèles ANN 
> Voir quelles valeurs inputs (possiblité de tout faire sur grass-hopper ? )
> Voir qu'est ce qu'on a besoin en sortie

Retour au sujet des méta-matériaux (GrassHopper) : 

Pour la prédiction des propriétés à partir de données tabulaires (les valeurs issues des simulations de GrassHopper), les algorithmes les plus pertinents sont les modèles à base d'arbres, surtout XGBoost et Random Forest, plutôt que les réseaux de neurones (ANN/deep learning).

La raison : sur du tabulaire, et sur des datasets de taille modeste (quelques centaines à milliers de lignes), les arbres sont plus précis, plus rapides à entraîner et demandent beaucoup moins de réglages que les réseaux de neurones. C'est confirmé par ces articles (Shwartz-Ziv & Armon 2021, « Deep Learning is Not All You Need » ), et côté métamatériaux : (Liu et al. 2024 "Machine-Learning-Based Characterization and Inverse Design of Metamaterials") prédit justement les propriétés effectives avec un Random Forest (R² > 0,98).

Enfin, simuler quelques milliers de métamatériaux sous Grasshopper serait optimal pour garantir un modèle réellement performant. 

Articles : 
    https://arxiv.org/pdf/2106.03253
    https://www.mdpi.com/1996-1944/17/14/3512

### Amélioration de l'article 

- Ajouter des détails sur le traitement / Analyse des données 
- Analyser le code existant 
- Réaliser l'entrainement des ANNs sur les nouvelles données traitées

Articles similaires : 
Application of machine learning techniques to predict the compressive strength of steel fiber reinforced concrete - https://www.nature.com/articles/s41598-025-16516-1

Prediction of mechanical properties of steel fibre-reinforced concrete under elevated temperature using ANN : https://www.frontiersin.org/journals/built-environment/articles/10.3389/fbuil.2025.1610115/full

Prediction of the compressive strength of lightweight concrete containing industrial and waste steel fibers using a multilayer neural network : https://aben.springeropen.com/articles/10.1186/s43251-023-00100-6