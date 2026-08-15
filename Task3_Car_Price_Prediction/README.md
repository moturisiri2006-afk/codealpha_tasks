# 🚗 Car Price Prediction

## 📌 Project Overview

This project was developed as part of the **CodeAlpha Data Science Internship**.

The goal of this project is to build a Machine Learning model that predicts the **selling price of a used car** based on different characteristics such as manufacturing year, present price, kilometers driven, fuel type, selling type, transmission, and previous owners.

The project follows a complete Machine Learning workflow, starting from data exploration and preprocessing to model training, prediction, and evaluation.

---

## 🎯 Objective

To develop a regression model that can estimate the selling price of a used car based on its available features.

### Target Variable

* `Selling_Price` — the price at which the used car was sold.

### Input Features

* `Year`
* `Present_Price`
* `Driven_kms`
* `Fuel_Type`
* `Selling_type`
* `Transmission`
* `Owner`

`Car_Name` was excluded from the model because using individual car names would create many categorical values and is not necessary for this baseline regression approach.

---

## 📊 Dataset

The dataset contains information about used cars and their selling prices.

After removing duplicate records:

* **299 records**
* **9 original columns**
* **No missing values**
* **2 duplicate records removed**

### Important Dataset Observations

* Petrol cars make up the majority of the dataset.
* Manual transmission cars are much more common than automatic cars.
* Dealer-sold cars are more common than individually sold cars.
* Most cars have relatively lower selling prices, with a small number of high-priced cars.

---

## 🔎 Exploratory Data Analysis

Several visualizations were created to understand the dataset and identify relationships between features and selling price.

### Key Findings

**1. Year vs Selling Price**

Newer cars generally tend to have higher selling prices than older cars.

**2. Present Price vs Selling Price**

A strong positive relationship was observed between present price and selling price.

The correlation between the two variables was approximately **0.88**, making `Present_Price` one of the most useful features for prediction.

**3. Driven Kilometers vs Selling Price**

The relationship was relatively weak and scattered in this dataset.

**4. Fuel Type**

Diesel cars generally showed higher selling-price distributions than Petrol cars, although CNG had very few observations.

**5. Selling Type**

Dealer-sold cars generally showed higher selling prices than individually sold cars.

**6. Transmission**

Automatic cars generally showed higher selling prices than manual cars in the dataset.

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

1. Inspected the dataset structure and data types.
2. Checked for missing values.
3. Identified and removed duplicate records.
4. Removed `Car_Name` from the model features.
5. Separated input features (`X`) from the target (`y`).
6. Converted categorical variables into numerical values using **One-Hot Encoding**.
7. Split the dataset into training and testing sets.

### Train-Test Split

* **80%** training data
* **20%** testing data

A fixed `random_state=42` was used to make the split reproducible.

---

## 🤖 Machine Learning Model

### Linear Regression

**Linear Regression** was selected as the baseline regression algorithm because the objective is to predict a continuous numerical value — the selling price.

The model learns the relationship between the input features and the target variable and then uses those learned relationships to predict prices for unseen cars.

---

## 📈 Model Evaluation

The trained model was evaluated using the following metrics:

| Metric                         |    Result |
| ------------------------------ | --------: |
| Mean Absolute Error (MAE)      | **1.216** |
| Mean Squared Error (MSE)       | **3.481** |
| Root Mean Squared Error (RMSE) | **1.866** |
| R² Score                       | **0.849** |

### Interpretation

The model achieved an **R² score of approximately 0.85**, meaning it explains around **85% of the variation in selling prices** in the test dataset.

The MAE of approximately **1.22** indicates that the model's predictions differ from the actual selling prices by about **1.22 price units on average**. Since the dataset prices are represented in lakhs, this corresponds to approximately **₹1.22 lakh average absolute error**.

The Actual vs Predicted visualization also shows a clear positive relationship between the model's predictions and the actual selling prices.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas** — data manipulation and analysis
* **NumPy** — numerical operations
* **Matplotlib** — data visualization
* **Seaborn** — statistical visualization
* **Scikit-learn** — preprocessing, model training, and evaluation
* **Jupyter Notebook** — development and experimentation

---

## 📁 Project Structure

```text
Task3_Car_Price_Prediction/
│
├── data/
│   └── car data.csv
│
├── images/
│   ├── actual_vs_predicted.png
│   ├── fuel_type_distribution.png
│   ├── present_price_vs_selling_price.png
│   ├── selling_price_distribution.png
│   ├── selling_type_distribution.png
│   └── transmission_distribution.png
│
├── notebook/
│   └── Car_Price_Prediction.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/moturisiri2006-afk/codealpha_tasks.git
```

### 2. Navigate to the project

```bash
cd codealpha_tasks/Task3_Car_Price_Prediction
```

### 3. Install the required libraries

```bash
pip install -r requirements.txt
```

### 4. Open the notebook

```bash
jupyter notebook
```

Open:

```text
notebook/Car_Price_Prediction.ipynb
```

Run the notebook cells in order to reproduce the analysis and model results.

---

## 📌 Conclusion

This project demonstrates an end-to-end Machine Learning workflow for predicting used-car selling prices.

The analysis showed that **Present Price** has the strongest relationship with the selling price among the numerical features considered. After preprocessing the data and encoding categorical variables, a Linear Regression model was trained and evaluated.

With an **R² score of approximately 0.85**, the model provides a reasonable baseline for used-car price prediction.

Future improvements could include experimenting with additional regression algorithms such as **Random Forest Regression, Gradient Boosting, or XGBoost**, along with hyperparameter tuning and additional feature engineering.


