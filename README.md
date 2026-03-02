# 🧠 Stroke Status Prediction

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)

---

## 📌 Project Overview

This project aims to predict whether a patient is at risk of having a stroke based on health and demographic data. The prediction model is built using the **K-Nearest Neighbors (KNN)** algorithm, with class imbalance handled using **SMOTE (Synthetic Minority Oversampling Technique)**.

Stroke is one of the leading causes of death and disability worldwide. Early detection and risk prediction can play a crucial role in preventing stroke-related complications. This project demonstrates how machine learning can be applied to support early diagnosis based on patient health records.

---

## 📂 Dataset

- **Source**: [Kaggle - Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)
- **File**: `healthcare-dataset-stroke-data.csv`
- **Size**: 5,110 rows × 12 columns
- **Target Variable**: `stroke` (0 = No Stroke, 1 = Stroke)

### Features Description

| Feature | Type | Description |
|---|---|---|
| `id` | int | Unique patient identifier |
| `gender` | categorical | Patient's gender (Male / Female / Other) |
| `age` | int | Patient's age |
| `hypertension` | binary | Whether the patient has hypertension (0 = No, 1 = Yes) |
| `heart_disease` | binary | Whether the patient has heart disease (0 = No, 1 = Yes) |
| `ever_married` | categorical | Marital status (Yes / No) |
| `work_type` | categorical | Type of occupation |
| `Residence_type` | categorical | Type of residence area (Urban / Rural) |
| `avg_glucose_level` | float | Average blood glucose level |
| `bmi` | float | Body Mass Index |
| `smoking_status` | categorical | Smoking status |
| `stroke` | binary | Target — whether the patient had a stroke (0 = No, 1 = Yes) |

---

## 🔧 Project Workflow

```
Data Understanding → Data Preparation → EDA → Modelling (KNN) → Evaluation → Oversampling (SMOTE) → Re-evaluation
```

### 1. 📊 Data Understanding
Exploring the structure of the dataset, checking data types, identifying missing values, and understanding the distribution of each feature.

### 2. 🔧 Data Preparation
- Handling missing values in the `bmi` column using the **mean** value
- **Binning** the `age`, `avg_glucose_level`, and `bmi` features into meaningful categories
- **Label Encoding** for categorical features

### 3. 📈 Exploratory Data Analysis (EDA)
Visualizing patterns and extracting insights from the data, including:
- Distribution of stroke vs. non-stroke patients
- Age distribution of stroke patients
- Stroke cases by gender, occupation, marital status, and residence type
- Relationship between hypertension, heart disease, and stroke
- Effect of BMI and blood glucose levels on stroke risk
- Stroke cases by smoking status

### 4. 🤖 Modelling — K-Nearest Neighbors (KNN)
- Features and target variable are separated
- Data is split into **70% training** and **30% testing**
- The best value of `k` is selected using **Cross Validation** (k = 1 to 20)
- Model is trained and evaluated on the test set

### 5. ⚖️ Oversampling with SMOTE
The dataset is highly imbalanced (~5% stroke-positive). To address this:
- **SMOTE** is applied to synthesize new samples for the minority class
- The model is retrained and re-evaluated on the balanced dataset

---

## 📊 Key Findings from EDA

- **Elderly patients** have a significantly higher risk of stroke compared to younger age groups
- Patients with **both hypertension and heart disease** show the highest stroke occurrence
- **High blood glucose levels** are strongly associated with stroke risk
- Stroke cases are slightly more common in **married patients**
- Stroke occurs across all residence types (Urban & Rural) with similar distribution

---

## ✅ Model Performance

### Before SMOTE
| Metric | Value |
|---|---|
| Accuracy | *See notebook output* |
| Note | Model biased toward majority class (No Stroke) |

### After SMOTE
| Metric | Value |
|---|---|
| Accuracy | *See notebook output* |
| Improvement | Higher recall and F1-score for stroke-positive class |

> 📝 Full confusion matrix and classification report are available in the notebook.

---

## 🛠️ Tools & Libraries

| Library | Purpose |
|---|---|
| `pandas` | Data manipulation and analysis |
| `numpy` | Numerical computation |
| `plotly.express` | Interactive data visualization |
| `scikit-learn` | Machine learning (KNN, train-test split, cross validation, evaluation metrics) |
| `imbalanced-learn` | SMOTE for handling imbalanced data |

---

## 🚀 How to Run

1. **Clone this repository**
   ```bash
   git clone https://github.com/your-username/stroke-status-prediction.git
   cd stroke-status-prediction
   ```

2. **Install required libraries**
   ```bash
   pip install pandas numpy plotly scikit-learn imbalanced-learn
   ```

3. **Download the dataset** from [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) and place `healthcare-dataset-stroke-data.csv` in the project directory

4. **Open and run the notebook**
   ```bash
   jupyter notebook Prediksi_Status_Stroke.ipynb
   ```

---

## 📁 Project Structure

```
stroke-status-prediction/
│
├── Prediksi_Status_Stroke.ipynb   # Main notebook
├── healthcare-dataset-stroke-data.csv  # Dataset (download from Kaggle)
└── README.md                      # Project documentation
```

---

## 👤 Author

**Your Name**
- GitHub: [@fathan-alf](https://github.com/fathan-alf)
- LinkedIn: [Fathan Alfariel Adhyaksa](https://www.linkedin.com/in/fathan-alfariel)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
