# Projet 11 : Étude de marché à l'export (ACP et clustering)

### Contexte
**La Poule qui Chante** (entreprise fictive) veut exporter son poulet bio et cherche les marchés les plus attractifs, sans aucune présélection de pays.

**Mon objectif :** laisser les données désigner les cibles. Où existe déjà une demande en volaille importée ? Quels pays ont le pouvoir d'achat pour un produit bio premium ? Comment regrouper les pays pour cibler efficacement ?

### Missions réalisées
* **Préparation des données :** croisement de trois sources FAO et Banque mondiale en un jeu de **168 pays et 12 variables**, sans valeur manquante. Variables choisies selon le cadre PESTEL, dont 5 construites par feature engineering (ratios, indicateurs composites).
* **ACP :** réduction des 12 variables à **3 axes (60,6 % de variance expliquée)**. Le premier axe oppose les pays riches et urbains aux grands pays agricoles, le second les pays dépendants des importations de volaille aux pays autosuffisants.
* **Clustering :** CAH (méthode de Ward) et K-means (K testé via silhouette, Davies-Bouldin et méthode du coude). Les deux convergent vers **4 groupes**, avec plus de 90 % de concordance confirmée par l'Adjusted Rand Index. Le Brésil et les États-Unis, premiers exportateurs mondiaux, ont été exclus : ce sont des concurrents, pas des cibles.
* **Priorisation :** distance au centroïde pour classer les pays au sein du groupe cible.

### Résultats
* **30 pays** en cible prioritaire (importateurs structurellement dépendants).
* Recommandations sur trois horizons : groupe prioritaire à court terme, marchés développés avec une offre premium à moyen terme, marchés émergents à surveiller à long terme.

### Compétences & Outils
* **Langage :** Python
* **Librairies :** Pandas, Scikit-learn
* **Techniques :** ACP, CAH, K-means, Adjusted Rand Index, analyse PESTEL

### Reproduire l'analyse
Les données brutes sont dans `data-raw/`. Pour exécuter les notebooks, placez ces fichiers dans le même dossier que le notebook. Le fichier `DisponibiliteAlimentaire_2017.csv` (bilans alimentaires de la FAO, 2017), lu par le premier notebook, dépasse la taille autorisée par GitHub : il est téléchargeable sur FAOSTAT, le portail de données de la FAO.

### Limites
Données de 2017, analyse purement quantitative : barrières non tarifaires et logistique à intégrer avant tout engagement commercial.

<img src="images/Capture d'écran 2026-06-26 142716.png" width="500px"><img src="images/Capture d'écran 2026-06-26 142956.png" width="500px">

---
📂 Dossier complet sur mon portfolio : [remydaura.github.io/p11.html](https://remydaura.github.io/p11.html)

*Ce projet fait partie de la formation Data Analyst d'OpenClassrooms.*
