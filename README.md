# US Flights Delay & Airport Data Analysis
### Exploratory Data Analysis, Flight Operations & Delay Patterns (2015 US Commercial Flights)

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458.svg?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Seaborn-11557c.svg)](https://matplotlib.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626.svg?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Dataset](https://img.shields.io/badge/Kaggle-2015%20Flight%20Delays-20BEFF.svg?logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/usdot/flight-delays)

---

## 📌 Présentation du Projet & Contexte

Le secteur aérien commercial opère sous des contraintes logistiques intenses où la ponctualité des vols conditionne la rentabilité des compagnies et la satisfaction des passagers. Ce projet réalise une **analyse exploratoire approfondie (EDA)** sur les opérations des vols intérieurs aux États-Unis en 2015.

L'objectif est d'identifier les causes profondes des retards et annulations, d'évaluer la performance des aéroports et compagnies majeures, et de mettre en lumière les dynamiques de trafic aérien.

---

## 🛠️ Méthodologie & Pipeline de Traitement

### 1. Collecte & Évaluation de la Qualité (*Data Wrangling*)
* **Complétude & Données Manquantes :** Analyse systématique des variables `DEPARTURE_DELAY`, `ARRIVAL_DELAY`, `TAXI_OUT`, `TAXI_IN`, `CANCELLATION_REASON`.
* **Ségrégation Méthodologique :** Séparation des données en trois tables étanches pour ne pas fausser les métriques temporelles :
  1. *Cleaned Flights :* Vols réguliers ayant atterri sans déroutement ni annulation.
  2. *Canceled Flights :* Vols annulés (analyse des motifs météo, compagnie, sécurité).
  3. *Diverted Flights :* Vols déroutés vers un autre aéroport.
* **Précision & Nettoyage :** Imputation par la médiane conditionnelle et suppression des colonnes à plus de 30% d'absence.

### 2. Analyse Statistique Multidimensionnelle
* **Univariée :** Distribution des fréquences de vols par aéroport de départ, compagnie et destination.
* **Bivariée :** Corrélations entre distance de vol, durée de taxi (*taxi-out / taxi-in*), temps de vol effectif et retard à l'arrivée.
* **Multivariée :** Analyse croisée de l'influence combinée de la météo, de la saturation des hubs majeurs (Chicago ORD, Atlanta ATL, Dallas DFW, Los Angeles LAX) et des saisons sur les retards.

---

## 🔍 Principaux Enseignements de l'Analyse

1. **Saturation des Hubs Aériens :**
   * Les aéroports à fort trafic comme **Chicago O'Hare (ORD)** et **Atlanta (ATL)** présentent une variance de retard au départ et un temps de roulage (*taxi-out*) nettement plus dispersés que la moyenne nationale en raison de goulots d'étranglement au décollage.
2. **Corrélations Distance & Durée :**
   * L'analyse met en évidence des clusters de liaisons distincts (vols régionaux courts < 500 miles vs vols transcontinentaux > 2 500 miles), chaque catégorie ayant des profils de retards spécifiques.
3. **Motifs d'Annulation :**
   * Les conditions météorologiques défavorables dominent les causes d'annulation en hiver, tandis que les incidents techniques et opérationnels transporteur pèsent de façon plus uniforme tout au long de l'année.

---

## 📁 Structure du Répertoire

```text
├── 2015-flights-data-analysis.ipynb  <- Notebook d'analyse complet documenté et exécuté
├── airlines.csv                      <- Référentiel des compagnies aériennes (code IATA & nom)
├── airports.csv                      <- Référentiel des aéroports américains (coordonnées, ville)
├── rapport_final.pdf                 <- Rapport d'étude synthétique complet
└── README.md                         <- Présentation et documentation du projet
```

---

## 🚀 Installation & Exécution

```bash
git clone https://github.com/khaoulasaidi49-beep/Air-port-.git
cd Air-port-
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook 2015-flights-data-analysis.ipynb
```

---
*Projet d'Analyse de Données Aériennes – Réalisé avec Python*
