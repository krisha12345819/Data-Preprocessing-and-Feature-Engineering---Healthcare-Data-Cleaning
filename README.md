# 🏥 Patient Health Data Cleanser

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logo=python&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

A comprehensive data preprocessing pipeline for patient health records, covering missing value imputation, outlier detection, and data preparation for machine learning.

---

## 🔗 Quick Access

| Resource | Description | Link |
|----------|-------------|------|
| 📓 Notebook | Complete data preprocessing pipeline | [Open Notebook](./patient_health_data_cleanser.ipynb) |
| 📊 Dataset | Raw healthcare dataset used in project | [View Dataset](./patient_health_records.csv) |
| 📄 Report | Detailed explanation and analysis | [Read Report](./Data_Cleanser_Project_Report.pdf) |
| 🖼️ Visuals | Charts and visual analysis | [Open Visuals Folder](./plots/) |

---

## 📋 Overview

This project processes a patient health dataset containing demographic and clinical features to improve data quality before downstream analysis or machine learning tasks.

**Dataset Features:**
- `patient_id` — Unique patient identifier
- `age` — Patient age
- `gender` — Patient gender (categorical)
- `region` — Geographic region (categorical)
- `bmi` — Body Mass Index
- `blood_pressure` — Blood pressure reading
- `cholesterol` — Cholesterol level
- `glucose` — Blood glucose level
- `disease_risk` — Target variable: `0` (Low Risk) / `1` (High Risk)

---

## 🎯 Objectives

- Identify and handle **missing values** using multiple imputation strategies
- Detect and treat **outliers** using statistical methods
- Compare different preprocessing approaches
- Prepare a clean dataset ready for **machine learning**

---

## 🗂️ Project Structure

```
patient-health-data-cleanser/
│
├── patient_health_data_cleanser.ipynb   # Main notebook with full pipeline
├── patient_health_records.csv           # Raw dataset
├── Data_Cleanser_Project_Report.pdf     # Project report
│
├── plots/
│   ├── bmi.png                          # BMI distribution histogram
│   ├── bmiOutlier.png                   # BMI outliers boxplot
│   ├── beforeOutlier.png                # Boxplot before outlier treatment
│   ├── afterOutlier.png                 # Boxplot after IQR treatment
│   └── zscore.png                       # Cholesterol vs Glucose scatter plot
│
└── README.md
```

---

## 🔧 Preprocessing Techniques

### Missing Value Imputation

| Method | Description |
|--------|-------------|
| **Simple Imputer** | Fills numerical missing values with mean/median; categorical with mode |
| **Most Frequent Imputation** | Replaces missing values with the most common value (mode) |
| **Missing Indicator + Random Sample** | Creates a missingness flag, then fills with randomly sampled existing values to preserve distribution |
| **KNN Imputer** | Uses K-Nearest Neighbors similarity to estimate missing values |
| **MICE Algorithm** | Multiple Imputation by Chained Equations — models each feature as a function of others through iterative regression |

### Outlier Detection & Treatment

| Method | Description |
|--------|-------------|
| **Z-Score** | Flags values beyond ±3 standard deviations from the mean; suited for normally distributed data |
| **IQR Method** | Detects outliers outside `Q1 − 1.5×IQR` and `Q3 + 1.5×IQR`; robust for skewed distributions |
| **Percentile Method** | Caps or removes values below the 1st and above the 99th percentile |
| **Winsorization** | Replaces extreme values with boundary thresholds rather than removing them |

---

## 📊 Key Visualizations

### 1. BMI Distribution
> Right-skewed histogram with KDE overlay — majority of patients fall in the 20–35 BMI range with extreme outliers reaching up to ~75.

![BMI Distribution](./plots/bmi.png)

---

### 2. BMI Outliers — Boxplot
> Multiple outliers visible on both the lower end (<10) and upper end (>50).

![BMI Outliers Boxplot](./plots/bmiOutlier.png)

---

### 3. Before Outlier Treatment
> Raw data showing the full spread of BMI values including extreme outliers on both sides.

![Before Outlier Treatment](./plots/beforeOutlier.png)

---

### 4. After Outlier Treatment (IQR Method)
> Outliers significantly reduced after applying IQR capping — distribution tightened to a healthy range of ~15–38.

![After Outlier Treatment](./plots/afterOutlier.png)

---

### 5. Cholesterol vs. Glucose Scatter Plot
> Reveals distinct clusters of anomalous data points with abnormally high glucose (400–560) and extreme cholesterol values (>450), indicating clinical extremes and potential data entry errors.

![Cholesterol vs Glucose](./plots/zscore.png)

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

### Run the Notebook

```bash
jupyter notebook patient_health_data_cleanser.ipynb
```

---

## 🛠️ Tech Stack

- **Python 3.x**
- **Pandas** — Data manipulation
- **NumPy** — Numerical operations
- **Scikit-learn** — Imputers (SimpleImputer, KNNImputer, IterativeImputer)
- **Matplotlib / Seaborn** — Visualizations

---

## 👤 Author

**Krisha Anghan**  
Project completed: March 27, 2026
