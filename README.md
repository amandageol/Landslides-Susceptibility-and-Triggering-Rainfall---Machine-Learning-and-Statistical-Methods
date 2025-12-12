🌎 Landslide Susceptibility & Rainfall Threshold Modeling — Angra dos Reis (RJ, Brazil)
📌 Statistical and Machine Learning Framework for Landslide Risk Assessment



🧭 Project Overview

This repository contains all scripts used in the scientific article:

“Application of Statistical Methods and Machine Learning for Landslide Susceptibility Mapping and Rainfall Threshold Definition: Case Study of the Central Region of Angra dos Reis - RJ, Brazil”



The repository provides a complete, transparent, and fully reproducible workflow integrating:

🔍 Statistical analyses (Frequency Ratio and Multiple Correspondence Analysis)

🤖 Machine Learning (Random Forest, SVM, Logistic Regression, LightGBM, XGBoost)

🧩 K-Means clustering as an auxiliary predictor

🗺️ Ordinary kriging for continuous probability surfaces

🌧️ Rainfall threshold definition for 24h, 48h, 72h, and 96h intervals

🛰️ Geospatial processing of Landslide Conditioning Factors (LCFs)

📚 Construction of a Landslide Scar Inventory (LSI)

Developed using open-source tools, this framework is designed to be technically accessible for municipal Civil Defense teams and risk management agencies.



⚙️ Prerequisites
🔧 Software Requirements

Python 3.10+

QGIS 3.x

Google Colab (recommended for notebooks)




📦 Key Python Libraries
pandas, numpy, geopandas, rasterio, scikit-learn,
lightgbm, xgboost, sklearn-extra, scipy,
matplotlib, seaborn, pykrige




📁 Input Data Required

Landslide Scar Inventory (2010–2023)

Eleven LCFs (slope, elevation, NDVI, NDBI, TWI, lithology, geotechnical zones, etc.)

São Bento rain gauge dataset

ASTER GDEM DEM




🚀 How to Use This Repository

1️⃣ Preprocessing (QGIS)
Classify continuous LCFs into 8 quantile-based classes
Keep original classes for categorical LCFs (lithology, geotechnical zones, aspect)

2️⃣ Dataset Assembly
5×5 m grid → statistical evaluation (FR and MCA)
30×30 m grid → susceptibility prediction
Balanced sampling of landslide and stable pixels

3️⃣ Statistical Analysis
Frequency Ratio → identification of irrelevant LCFs
Multiple Correspondence Analysis → multivariate interactions and dimensionality insights

4️⃣ Machine Learning Modeling
Models trained: RF, SVM, LR, XGB, LGB
K-Means cluster used as an additional predictor
Evaluation metrics:
    ROC-AUC
    False Negative Rate
    Accuracy

5️⃣ Susceptibility Mapping
Prediction at 30×30 m
Ordinary kriging interpolation
Six classification methods tested
CDF-based classification chosen as the optimal method

6️⃣ Rainfall Threshold Definition
Extract 24h–96h accumulated rainfall for each event
Compute mean and maximum rainfall per susceptibility class
Interpret hydrological triggering behavior



📂 Repository Structure
├── data/
│   ├── lsi/
│   ├── lcf_raw/
│   ├── lcf_processed/
│   └── rainfall/
│
├── notebooks/
│   ├── 01_FR_analysis.ipynb
│   ├── 02_MCA_analysis.ipynb
│   ├── 03_ML_training.ipynb
│   ├── 04_kriging_mapping.ipynb
│   └── 05_rainfall_thresholds.ipynb
│
├── scripts/
│   ├── preprocessing.py
│   ├── fr_calculation.py
│   ├── mca.py
│   ├── ml_models.py
│   ├── kriging.py
│   └── rainfall_analysis.py
│
├── results/
│   ├── maps/
│   ├── tables/
│   └── metrics/
│
└── README.md




📊 Key Results

🌟 Best-Performing Model
Random Forest + K-Means
ROC-AUC = 0.89
Lowest false negative rate

🗺️ Susceptibility Map
Using the CDF classification method:
Effectiveness = 0.896
Intermediate Entropy and GINI values
Best balance between discrimination and natural variability

📈 Kriging Validation
R² = 0.76

📬 Contact
Amanda Alves da Silva
Environmental Engineering PhD Candidate • Geological Engineer
Federal University of Rio de Janeiro (UFRJ)
📧 amandaalves@poli.ufrj.br