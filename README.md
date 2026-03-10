# 🏨 Hotel Data Analysis & Classification  
### Data Collection Lab – Technion

This repository contains our final project for the **Data Collection Lab** course at the **Technion – Israel Institute of Technology**.

The goal of this project is to **collect, unify, and analyze hotel listing data from multiple booking platforms** and apply **machine learning models** to predict hotel quality based on listing features.

The entire pipeline — from **data collection to model evaluation** — is implemented in a single notebook that can be executed with different dataset configurations.

---

# 📂 Repository Structure

```
.
├── Project_211585765_207730854_316148253.ipynb   # Main project notebook
├── Project_211585765_207730854_316148253.html    # Exported notebook (easy viewing)
├── scraping_agoda.py                             # Agoda data collection script
└── README.md
```

---

# 🌐 Data Sources

The dataset integrates hotel listings collected from multiple platforms:

- **Airbnb**
- **Booking**
- **Agoda**

Since each platform uses a different schema, the datasets were **cleaned, aligned, and merged** into a unified dataset called:

```
unified_df
```

**Shared and comparable features** were kept to ensure consistent modeling across all platforms.

Example features include:

- Review score / rating
- Price information
- Amenities
- Host / manager score
- Platform indicator
- Additional numerical and categorical attributes

---

# 🔄 Data Pipeline

The project follows the pipeline below:

```
Data Collection
        │
        ▼
Data Cleaning & Normalization
        │
        ▼
Dataset Alignment (Airbnb / Booking / Agoda)
        │
        ▼
Unified Dataset (unified_df)
        │
        ▼
Feature Engineering
        │
        ▼
Train/Test Split
        │
        ▼
Machine Learning Models
        │
        ▼
Model Evaluation
```

---

# ⚙️ Execution Modes (RUN_TABLE)

The notebook allows running experiments on different subsets of the dataset using the `RUN_TABLE` parameter.

| RUN_TABLE | Dataset Used |
|----------|--------------|
| `1` | Full dataset (all sources combined – not recommended due to runtime) |
| `2` | Combined datasets |
| `3` | Airbnb only |
| `4` | Booking only |
| `5` | Agoda only |

*Important Note:*  
To reproduce results, the notebook **must be executed separately for each RUN_TABLE configuration**.

---

# 🤖 Machine Learning Models

The project includes **three different types of models** applied to the hotel dataset:

### 1. Regression Models
The notebook includes regression-based modeling to predict continuous hotel rating scores.  
These models estimate the numerical target directly and help analyze feature effects on hotel ratings.

### 2. Neural Network Model
The project also includes a **deep learning approach** based on a **PyTorch MLP (Multi-Layer Perceptron)**.  
This model is trained on exported parquet data and evaluated separately using regression metrics such as **RMSE** and **R²**.

### 3. Classification Models
In addition to regression, the project includes classification models that convert hotel scores into discrete classes and predict the class label.

Including:
- Random Forest  
- Multinomial Logistic Regression  
- One-vs-Rest + Gradient Boosted Trees (GBT)

All models use the **same preprocessing and feature pipeline** to ensure fair comparison and allow evaluation of different approaches for predicting hotel quality categories.

---

# 📊 Model Evaluation

Models are evaluated using a **train/test split**:

- **95% Training**
- **5% Testing**

Evaluation includes comparison between models using appropriate metrics for each task, including regression metrics (such as **RMSE** and **R²**) and classification metrics (such as **accuracy**).

---

# ▶️ How to Run the Project

To successfully run the notebook, **all dataset files referenced in the code must be available in the working directory** when executing the notebook.

Before running the project, make sure that:

- All required data files are available
- The files are located in the **same working directory as the notebook**, or in the paths expected by the code

Then follow these steps:

1. Open the notebook:

```
Project_211585765_207730854_316148253.ipynb
```

2. Select the dataset configuration:

```
RUN_TABLE = ...
```

3. Run the notebook cells sequentially.

4. To reproduce all experiments, run the notebook multiple times with different `RUN_TABLE` values.

---

# 🛠 Data Collection

The file:

```
scraping_agoda.py
```

contains a scraping script used to collect hotel listing data from **Agoda** during the data collection phase.
Important: there are 2 more datasets not included here of Airbnb and Booking which part of the unified data set, due to copyrights we can't add them here.
---

# 👨‍💻 Authors

**Daniel Kats**  
**Saar Shabi**  
**Uri Shteinberg**

Technion – Israel Institute of Technology  

Course: **Data Collection Lab**

---

# 📌 Project Summary

This project demonstrates a full **data science workflow**:

- Data collection from real-world platforms
- Data normalization across different schemas
- Unified dataset creation
- Feature engineering
- Machine learning modeling
- Cross-platform comparison

The resulting system allows evaluating how well hotel quality can be predicted based on listing features across multiple booking platforms.
