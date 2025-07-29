# 🫐 Blueberry Yield Prediction - Kaggle Regression Challenge

This repository contains my solution for the [Blueberry Regression](https://www.kaggle.com/competitions/blueberry-regression-sentence/overview) Kaggle competition.  
The goal of this challenge is to accurately predict the **blueberry yield** (`yield`) based on environmental and agricultural data.  
It is a **regression task**, where the target is a continuous variable.


![uAWeWfDQVrFPdCgKmgZhX](https://github.com/user-attachments/assets/1452b282-4978-4a67-bc24-6eede040d9f2)


---

## 🗂️ Project Structure

```

project-root/
├── 📄 Blueberry.ipynb           # Main notebook: full ML pipeline from preprocessing to submission.
├── 📊 train.csv                 # Training dataset with features and target ('yield').
├── 🧪 test.csv                  # Test dataset: features for prediction.
├── 📝 sample_submission.csv     # Template for Kaggle submission.
├── 🚀 sub.csv                   # Submission from SGDRegressor.
├── 🚀 sub1.csv                  # Submission from RandomForestRegressor.
├── 🚀 sub2.csv                  # Submission from XGBRegressor.
└── 📜 README.md                 # Project documentation.

```


---

## 💻 Technologies Used

- **Language**: Python 3.x  
- **Environment**: Jupyter Notebook  

### 📦 Libraries

- `pandas`, `numpy` – Data manipulation  
- `matplotlib`, `seaborn` – Visualization  
- `scikit-learn` – Preprocessing & modeling (SGD, RF, pipelines, scaling)  
- `xgboost` – XGBoost Regressor  
- `GridSearchCV` – Hyperparameter tuning  
- `StandardScaler` – Normalization  
- `mean_absolute_error`, `mean_squared_error` – Model evaluation

---

## 📊 Dataset Description

Competition page: [Blueberry Regression](https://www.kaggle.com/competitions/blueberry-regression-sentence/overview)

- `train.csv`: Training data with the target variable `yield`
- `test.csv`: Unlabeled data for prediction
- `sample_submission.csv`: Required submission format

---

## 🔁 Workflow Summary

The `Blueberry.ipynb` notebook follows the full ML workflow:

### 1. Data Loading & Preprocessing
- Load `train.csv` and `test.csv`
- Drop the `id` column
- Apply `StandardScaler` to numerical features

### 2. Modeling
Three regression models were built and compared:

| Model Name             | Methodology             | Output File |
|------------------------|--------------------------|-------------|
| **SGD Regressor**      | Pipeline + GridSearchCV  | `sub.csv`   |
| **RandomForest**       | GridSearchCV             | `sub1.csv`  |
| **XGBoost**            | GridSearchCV             | `sub2.csv`  |

All models were evaluated using:
- **MAE** (Mean Absolute Error)  
- **RMSE** (Root Mean Squared Error)

### 3. Prediction & Submission
- Final predictions on the test set were saved as:
  - `sub.csv` → SGD Regressor
  - `sub1.csv` → Random Forest Regressor
  - `sub2.csv` → XGBoost Regressor

---

## 📈 Results Summary

| Model                  | Tuning Method         | Evaluation | Submission File  |    MAE   |   RMSE   |
|------------------------|-----------------------|------------|------------------|----------|----------|
| SGD Regressor          | GridSearchCV          | MAE / RMSE | `sub.csv`        |  269.94  |  388.11  |
| RandomForestRegressor  | GridSearchCV          | MAE / RMSE | `sub1.csv`       |  257.78  |  374.73  |
| XGBRegressor           | GridSearchCV          | MAE / RMSE | `sub2.csv`       |  257.40  |  373.27   |
 
---

## ⚙️ Installation

To install all required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
