# 🥊 Octagon Insights — MMA Fight Outcome Prediction

> An end-to-end machine learning pipeline that predicts MMA fight outcomes using historical fighter statistics and fight records.

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange.svg)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626.svg)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

🎥 **[Watch the project demo on YouTube](https://www.youtube.com/watch?v=6NuS92tVtZY)**

---

## 📖 Table of Contents
- [Overview](#-overview)
- [Dataset](#-dataset)
- [Methodology](#%EF%B8%8F-methodology)
- [Results](#-results)
- [Tech Stack](#-tech-stack)
- [Installation & Usage](#-installation--usage)
- [Project Structure](#-project-structure)
- [Authors](#-authors)
- [License](#-license)

---

## 🎯 Overview

**Octagon Insights** is a machine learning project developed for the **Introduction to Machine Learning** course at Hacettepe University. The project tackles a real-world sports analytics problem:

> *Given two MMA fighters, who is more likely to win in a hypothetical matchup?*

By engineering features from historical fighter statistics and fight records, training multiple classification models, and benchmarking their performance, the project delivers a predictor capable of simulating fights between any two fighters in the dataset.

---

## 📊 Dataset

The project uses two CSV files containing UFC fighter and fight data:

| File | Description |
|------|-------------|
| `raw_fighter_details.csv` | Per-fighter physical and performance statistics (height, reach, striking accuracy, takedown accuracy, takedown defense, etc.) |
| `raw_total_fight_data.csv` | Historical fight records, including matchups and outcomes |

### Preprocessing
- Handled missing values and inconsistent formatting (e.g. `Str_Acc`, `TD_Acc`, `TD_Def` percentages)
- Merged per-fighter statistics with fight-level records
- Engineered comparison features between fighter pairs

---

## ⚙️ Methodology

### Exploratory Data Analysis
- Distribution analysis of physical attributes and performance metrics
- Correlation analysis between features and fight outcomes
- Investigation of class balance and feature relevance

### Models Trained
| Model | Type |
|-------|------|
| Gradient Boosting | Ensemble |
| Random Forest | Ensemble |
| Logistic Regression | Linear |
| K-Nearest Neighbors | Instance-based |
| Support Vector Machine | Margin-based |

All models were evaluated with cross-validation and tuned via hyperparameter search.

---

## 📈 Results

| Model | Accuracy |
|-------|:--------:|
| **Gradient Boosting** | **0.72** |
| **Logistic Regression** | **0.72** |
| KNN (k = 20) | 0.66 |

**Gradient Boosting** and **Logistic Regression** delivered the best generalization, achieving **72% accuracy** on the held-out test set.

### Example Prediction
```python
chosen_model = models['Random Forest']
print(predict_winner("Alex Pereira", "Jon Jones", fighter_stats, chosen_model))
```

---

## 🛠 Tech Stack

- **Language:** Python 3.8+
- **ML Libraries:** scikit-learn, pandas, NumPy
- **Visualization:** matplotlib, seaborn
- **Environment:** Jupyter Notebook

---

## 🚀 Installation & Usage

1. **Clone the repository**
   ```bash
   git clone https://github.com/ozgun-koca/Octagon-Insights.git
   cd Octagon-Insights
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the notebook**
   ```bash
   jupyter notebook octagon_insights.ipynb
   ```

---

## 📁 Project Structure

```
.
├── octagon_insights.ipynb       # Main analysis & modeling notebook
├── raw_fighter_details.csv      # Fighter statistics dataset
├── raw_total_fight_data.csv     # Fight records dataset
├── requirements.txt             # Python dependencies
└── README.md                    # You are here
```

---

## 👥 Authors

This project presents an end-to-end machine learning pipeline for predicting MMA fight outcomes from historical fighter statistics. It covers data preprocessing, feature engineering, exploratory analysis, model training, hyperparameter tuning, evaluation, and technical reporting.


- **Özgün Serergün Koca** — [GitHub](https://github.com/ozgun-koca) · ozgunserergun@gmail.com
- **Kağan Canerik** — [GitHub](https://github.com/KaganCanerik)

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
