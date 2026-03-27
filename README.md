
<div align="center">

# 🏥 Patient Health Data Cleanser

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/Status-✅%20Completed-2ecc71?style=for-the-badge)

<br/>

> *✨ A comprehensive data preprocessing pipeline for patient health records —*
> *cleaning, imputing, detecting outliers, and preparing data for machine learning.*

</div>

---

## 🔗 Quick Access

<div align="center">

| 🔖 Resource | 📝 Description | 🌐 Link |
|:-----------:|:---------------:|:-------:|
| 📓 **Notebook** | Complete data preprocessing pipeline | [Open Notebook](./patient_health_data_cleanser.ipynb) |
| 📊 **Dataset** | Raw healthcare dataset used in project | [View Dataset](./patient_health_records.csv) |
| 📄 **Report** | Detailed explanation and analysis | [Read Report](./Data_Cleanser_Project_Report.pdf) |
| 🖼️ **Visuals** | Charts and visual analysis | [Open Visuals Folder](./plots/) |

</div>

---

## 📋 Overview

This project processes a **patient health dataset** containing demographic and clinical features to improve data quality before downstream analysis or machine learning tasks.

<details>
<summary>📂 <b>Dataset Features — Click to Expand</b></summary>

<br/>

| 🏷️ Feature | 📌 Type | 📖 Description |
|:----------:|:-------:|:--------------:|
| `patient_id` | 🔑 ID | Unique patient identifier |
| `age` | 🔢 Numerical | Patient age |
| `gender` | 🏷️ Categorical | Patient gender |
| `region` | 🌍 Categorical | Geographic region |
| `bmi` | ⚖️ Numerical | Body Mass Index |
| `blood_pressure` | 💉 Numerical | Blood pressure reading |
| `cholesterol` | 🩸 Numerical | Cholesterol level |
| `glucose` | 🍬 Numerical | Blood glucose level |
| `disease_risk` | 🎯 Target | `0` = Low Risk · `1` = High Risk |

</details>

---

## 🎯 Objectives

```
🔍  Identify and handle missing values using multiple imputation strategies
📉  Detect and treat outliers using robust statistical methods
⚖️  Compare different preprocessing approaches side-by-side
🤖  Prepare a clean dataset ready for machine learning
```

---

## 🗂️ Project Structure

```
📦 patient-health-data-cleanser/
│
├── 📓 patient_health_data_cleanser.ipynb   ← Main notebook with full pipeline
├── 📊 patient_health_records.csv           ← Raw dataset (500+ records)
├── 📄 Data_Cleanser_Project_Report.pdf     ← Project report & analysis
│
├── 📁 plots/
│   ├── 🖼️  bmi.png                         ← BMI distribution histogram
│   ├── 🖼️  bmiOutlier.png                  ← BMI outliers boxplot
│   ├── 🖼️  beforeOutlier.png               ← Boxplot before treatment
│   ├── 🖼️  afterOutlier.png                ← Boxplot after IQR treatment
│   └── 🖼️  zscore.png                      ← Cholesterol vs Glucose scatter
│
└── 📝 README.md
```

---

## 🔧 Preprocessing Techniques

### 💊 Missing Value Imputation

| 🧪 Method | 📖 Description |
|:---------:|:--------------|
| 🟦 **Simple Imputer** | Fills numerical NaNs with mean/median; categorical with mode |
| 🟩 **Most Frequent Imputation** | Replaces missing values with the most common value (mode) |
| 🟨 **Missing Indicator + Random Sample** | Creates a missingness flag, then fills by randomly sampling existing values |
| 🟧 **KNN Imputer** | Uses K-Nearest Neighbors similarity to estimate missing values |
| 🟥 **MICE Algorithm** | Multiple Imputation by Chained Equations — iterative regression-based imputation |

<br/>

### 🚨 Outlier Detection & Treatment

| 🔬 Method | 📖 Description |
|:---------:|:--------------|
| 📐 **Z-Score** | Flags values beyond ±3 standard deviations; best for normal distributions |
| 📦 **IQR Method** | Detects values outside `Q1 − 1.5×IQR` / `Q3 + 1.5×IQR`; robust for skewed data |
| 📏 **Percentile Method** | Caps/removes values below 1st and above 99th percentile |
| 🪄 **Winsorization** | Replaces extremes with boundary thresholds — no data is lost |

---

## 📊 Key Visualizations

### 📈 1. BMI Distribution
> 💡 Right-skewed histogram with KDE overlay — most patients in the **20–35 BMI range** with extreme outliers reaching up to **~75**.

![BMI Distribution](./plots/bmi.png)

---

### 📦 2. BMI Outliers — Boxplot
> 💡 Multiple outliers visible on both the **lower end (<10)** and **upper end (>50)** before any treatment.

![BMI Outliers Boxplot](./plots/bmiOutlier.png)

---

### ❌ 3. Before Outlier Treatment
> 💡 Raw BMI data showing the **full spread** of values including extreme outliers on both sides of the distribution.

![Before Outlier Treatment](./plots/beforeOutlier.png)

---

### ✅ 4. After Outlier Treatment (IQR Method)
> 💡 Outliers significantly reduced after IQR capping — distribution **tightened to 15–38**, a clinically meaningful range.

![After Outlier Treatment](./plots/afterOutlier.png)

---

### 🔵 5. Cholesterol vs. Glucose Scatter Plot
> 💡 Reveals distinct anomalous clusters — **glucose 400–560** and **cholesterol >450** indicating data entry errors or clinical extremes.

![Cholesterol vs Glucose](./plots/zscore.png)

---

## 🚀 Getting Started

### ⚙️ Prerequisites

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

### ▶️ Run the Notebook

```bash
jupyter notebook patient_health_data_cleanser.ipynb
```

---

## 🛠️ Tech Stack

<div align="center">

| 🔧 Tool | 💡 Purpose |
|:-------:|:----------:|
| 🐍 **Python 3.x** | Core programming language |
| 🐼 **Pandas** | Data manipulation & cleaning |
| 🔢 **NumPy** | Numerical operations |
| 🤖 **Scikit-learn** | SimpleImputer · KNNImputer · IterativeImputer |
| 📊 **Matplotlib** | Static visualizations |
| 🎨 **Seaborn** | Statistical data visualization |

</div>

---

## 👩‍💻 Author

<div align="center">

### ✨ Krisha Anghan

📅 **Project Completed:** March 27, 2026

*Made with ❤️ and a lot of 🧹 data cleaning!*

</div>
