

# 🎓 Student Attendance Prediction System

## 🚀 Overview

Predicting student attendance is crucial for educational institutions to optimize resource allocation, plan lecture halls, and identify trends in student engagement.

This project utilizes **Machine Learning** to predict the **Attendance Percentage** of a class based on various temporal, historical, and categorical features (like subject, time of day, and holidays). We explore multiple regression techniques, perform rigorous Feature Engineering, and evaluate models to find the most accurate predictor.

-----

## 📂 Dataset Details

The dataset (`featured_attendance_data.xlsx`) contains historical attendance records enriched with derived features.

**Key Features:**

  * **📅 Temporal:** `Year`, `Day_of_Week`, `Time_of_Day` (Morning/Evening).
  * **🏫 Academic:** `Subject` (Core CS, AI, WebDev, etc.), `Batch_Number`.
  * **📈 Historical Trends:**
      * `Prev_Subject_Attendance`: Attendance of the previous lecture.
      * `Rolling_Subject_Attendance_3`: Moving average of the last 3 classes.
      * `Subject_Attendance_Trend`: The trajectory of attendance (increasing/decreasing).
  * **🎉 External Factors:** `Next_day_holiday`, `Event_on_that_day`.

**Target Variable:** `Attendance_Percentage` 🎯

-----

## 🛠️ Tech Stack & Workflow

### 1\. Data Preprocessing 🧹

  * **Cleaning:** Handling dropped rows and renaming columns for clarity.
  * **Type Conversion:** Converting categorical columns to numerical using **One-Hot Encoding** (e.g., Subjects, Batches) and Binary Mapping (Yes/No).
  * **Scaling:** Applied `StandardScaler` to numerical features to normalize distribution.

### 2\. Feature Selection 🔍

We used **RFE (Recursive Feature Elimination)** to strip down the dataset to the most impactful features. This helped reduce noise and improve model training times without sacrificing accuracy.

### 3\. Models Implemented 🤖

We benchmarked several algorithms to find the best fit:

1.  **Linear Regression** (Baseline)
2.  **Ridge & Lasso Regression** (Regularization L1/L2)
3.  **ElasticNet**
4.  **Random Forest Regressor** 🌲
5.  **Gradient Boosting Regressor**
6.  **XGBoost** 🚀
7.  **LightGBM** ⚡

-----

## 📊 Model Performance & Results

After training and testing, we evaluated the models using **$R^2$ Score**, **MAE** (Mean Absolute Error), and **MSE** (Mean Squared Error).

| Model | $R^2$ Score | MAE | MSE |
| :--- | :---: | :---: | :---: |
| **Linear Regression (OLS)** | **\~0.84** | **4.87** | **49.03** |
| LightGBM | 0.71 | 5.60 | 77.07 |
| Gradient Boosting | 0.68 | 5.57 | 83.35 |
| Random Forest | 0.69 | 5.17 | 82.49 |
| XGBoost | 0.60 | 6.16 | 105.14 |

> **💡 Insight:** Interestingly, **Linear Regression** outperformed complex boosting models on this specific dataset. This suggests that the relationships between our engineered trend features and the target variable are highly linear\!

-----

## 📈 Visualizations

The project includes detailed plots to visualize model performance:

  * **Actual vs. Predicted Scatter Plots:** To see how close our predictions are to reality.
  * **Feature Importance (RFE):** Identifying which factors (like 'Previous Attendance' or 'Day of Week') drive students to skip or attend class.

*(You can find these plots generated within the notebook)*

-----

## ⚙️ How to Run

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/YOUR_USERNAME/Student-Attendance-Prediction.git
    cd Student-Attendance-Prediction
    ```

2.  **Install dependencies:**

    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn xgboost lightgbm
    ```

3.  **Run the Notebook:**
    Open `Proxy(ML_Project).ipynb` in Jupyter Notebook or Google Colab and run all cells.

    *Note: The dataset is automatically downloaded inside the notebook via `gdown`.*

-----

## 🔮 Future Improvements

  * **Time-Series Analysis:** Treating the data as a sequence to capture seasonality better.
  * **Hyperparameter Tuning:** Using `GridSearchCV` or `Optuna` to squeeze more performance out of the Boosting models.
  * **Deployment:** Building a simple Streamlit or Flask app where teachers can input class details and get an attendance forecast.

-----

## 🤝 Contributing

Contributions, issues, and feature requests are welcome\! 

-----

<div align="center"\>
<b\>⭐️ Don't forget to star this repo if you found it useful ⭐️</b\>
</div\>

```
```
