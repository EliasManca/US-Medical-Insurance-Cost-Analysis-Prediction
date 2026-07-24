# 🏥 US Medical Insurance Cost Analysis & Prediction

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Library](https://img.shields.io/badge/Library-Pandas%20%7C%20Seaborn%20%7C%20Scikit--Learn-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📌 Business Overview
Health insurance companies need accurate charge prediction models to price policies competitively while maintaining profitability. Traditional linear models often fail to capture non-linear interactions, such as the compound effect of smoking combined with high BMI.

This project analyzes the **US Medical Insurance dataset** to uncover key driver variables behind medical expenses and builds a Machine Learning pipeline to predict annual charges for new customers.

---

## 📊 Key Findings & Exploratory Data Analysis (EDA)
* **Smoking & BMI Interaction:** Smoking is the single strongest determinant of high medical charges. However, smokers with a **BMI $\ge 30$ (obese)** face exponentially higher costs (averaging over **$40,000/year**) compared to non-smokers or non-obese smokers.
* **Age Factor:** Medical charges increase steadily with age at an average rate of **~$250/year**, holding other factors constant.
* **Geographic & Gender Impact:** Region and gender show minor direct impacts on overall pricing compared to lifestyle indicators (smoking, BMI).

---

## ⚙️ Machine Learning Pipeline & Performance

Three regression models were trained and evaluated using **80/20 train-test split** and **cross-validation**:

1. **Linear Regression:** Baseline model (captures linear relationships, but misses non-linear feature interactions).
2. **Decision Tree Regressor:** Captures non-linear thresholds, but prone to overfitting.
3. **Random Forest Regressor (Selected Model):** Combines an ensemble of decision trees to stabilize variance and increase accuracy.

### Model Evaluation Results

| Model | $R^2$ Score | MAE ($) | RMSE ($) |
| :--- | :---: | :---: | :---: |
| Linear Regression | 0.75 | ~$4,200 | ~$6,100 |
| Decision Tree | 0.78 | ~$3,100 | ~$5,400 |
| **Random Forest (Final)** | **$\ge 0.86$** | **~$2,500** | **~$4,800** |

---

## 🎯 Business Impact & Value
* **High Accuracy ($R^2 \ge 0.86$):** The Random Forest model explains **over 86% of the variance** in annual medical charges using just 6 primary features.
* **70%+ Error Reduction:** Compared to a baseline strategy using overall historical averages (MAE ~$9,000), our model lowers the mean absolute prediction error down to **~$2,500**.
* **Risk Management:** Allows underwriters to quickly flag high-risk demographic combinations (e.g., Obese + Smoker) and adjust premiums accurately.

---

## 🛠️ Tech Stack & Tools
* **Language:** Python
* **Environment:** Google Colab
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Seaborn, Matplotlib
* **Machine Learning:** Scikit-Learn (`RandomForestRegressor`, `StandardScaler`, `train_test_split`)

---

## 🚀 How to Run the Project

You can run this project directly in your browser without installing anything locally:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1NtMJcLeXIJMLqQKH-WJigOS_DmcFa_F5)

1. Click the **"Open In Colab"** badge above.
2. Go to **Runtime > Run all** (or press `Ctrl + F9`).
3. Make sure to upload the `insurance.csv` file to the Colab environment session storage when prompted, or run the automated dataset download step in the notebook.
