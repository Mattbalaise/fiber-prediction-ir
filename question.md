### 1. Incohérence : nombre de neurones d'entrée

**Citation du papier :**
> "the input layer comprises 24 neurons"

**Observation :**
La figure associée montre seulement **17 neurones** d'entrée.

![alt text](image.png)


### 2. Dataleakage : FS/CS

> Vérifier si FS est supprimé dans l'entrainement CS et inversement 

Corrélation à 0.95 entre les variables cibles : 
![alt text](image-1.png)


### 3 : FS

> Est-ce que pour le FS on a utilisé un Random Forest ? : "the Random Forest-predicted"


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