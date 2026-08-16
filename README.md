# ✈️ Flight Price Prediction

## 📌 Project Overview

This project focuses on analyzing flight ticket prices and building a **Linear Regression model** to predict flight prices based on flight-related features.

The project includes data preparation, exploratory data analysis (EDA), outlier detection and removal, feature selection, categorical encoding, feature scaling, model building, and model evaluation.

---

## 🎯 Objective

The main objective of this project is to understand the factors that influence flight prices and build a regression model that can predict flight prices using relevant features.

---

## 📊 Dataset

The dataset initially contained **300,153 records and 12 columns**.

The dataset includes information related to:

* Airline
* Flight
* Source city
* Destination city
* Departure time
* Arrival time
* Number of stops
* Travel class
* Duration
* Days left until departure
* Flight price

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Statsmodels
* Google Colab
* Jupyter Notebook

---

## 🧹 Data Preparation

The following preprocessing steps were performed:

* Removed the irrelevant `Unnamed: 0` index column.
* Converted `days_left` and `price` to appropriate numerical data types.
* Checked for duplicate records.
* Checked for missing values.
* Examined the number of unique values in each column.

No duplicate records or missing values were found during the initial data-quality checks.

---

## 🔍 Exploratory Data Analysis

EDA was performed to understand the relationship between flight characteristics and ticket prices.

### Categorical Analysis

Count plots were used to analyze:

* Airline
* Source city
* Destination city
* Departure time
* Arrival time
* Stops
* Class

### Numerical Analysis

Histograms and box plots were used to understand the distributions of:

* Duration
* Days left
* Price

### Bivariate Analysis

Box plots and scatter plots were used to investigate the relationship between flight features and price.

Some important observations included:

* Business-class flights were considerably more expensive than Economy flights.
* Number of stops had a noticeable relationship with price.
* Vistara and Air India generally showed higher prices compared with some other airlines.
* Longer flight duration was associated with higher prices.
* Flight prices tended to be higher when fewer days were left before departure.

---

## 🚨 Outlier Detection

The **Interquartile Range (IQR)** method was used to identify outliers in numerical variables.

Initial outliers detected:

| Feature   | Outliers |
| --------- | -------: |
| Duration  |    2,110 |
| Days Left |        0 |
| Price     |      123 |

A total of **2,232 rows** were removed.

Dataset size changed from:

**300,153 → 297,921 records**

---

## ⚙️ Feature Selection

Based on the EDA, the following features were selected for the model:

### Categorical Features

* `airline`
* `departure_time`
* `stops`
* `class`

### Numerical Features

* `duration`
* `days_left`

The following columns were excluded from the final model:

* `source_city`
* `destination_city`
* `arrival_time`
* `flight`

These were considered less useful or redundant based on the analysis.

---

## 🔄 Feature Engineering

Categorical variables were converted into numerical variables using **one-hot encoding**.

`drop_first=True` was used to reduce multicollinearity among the encoded categorical variables.

The numerical features:

* `duration`
* `days_left`

were standardized using **StandardScaler**.

---

## 🤖 Linear Regression Model

An **Ordinary Least Squares (OLS) Linear Regression** model was built using Statsmodels.

### Training Process

1. Selected features and target variable.
2. Applied one-hot encoding to categorical variables.
3. Converted encoded variables to numerical format.
4. Split the dataset into training and testing sets.
5. Applied StandardScaler to numerical features.
6. Added a constant term for the OLS model.
7. Trained the Linear Regression model.

### Train-Test Split

* Training data: **80%**
* Testing data: **20%**
* Random state: **42**

---

## 📈 Model Performance

The model achieved the following results on the test dataset:

| Metric   |        Result |
| -------- | ------------: |
| MAE      |      4,589.19 |
| MSE      | 46,785,249.22 |
| RMSE     |      6,839.97 |
| R² Score |    **0.9093** |

The **R² score of approximately 0.91** indicates that the model explains around **90.9% of the variation in flight prices** within the evaluated data.

---

## 💡 Key Insights

The analysis identified several important factors associated with flight prices:

* **Travel class** has a strong influence on price.
* **Number of stops** affects ticket pricing.
* **Flight duration** has a positive relationship with price.
* **Days left before departure** has a negative relationship with price.
* Airline also contributes to differences in flight prices.

---

## 📁 Project Structure

```text
flight-price-prediction/
│
├── Flight_Price_Prediction.ipynb
└── README.md
```

---

## 🚀 Future Improvements

Possible improvements for future versions of this project include:

* Testing additional regression algorithms.
* Comparing Linear Regression with Random Forest and Gradient Boosting models.
* Performing hyperparameter tuning.
* Applying more advanced feature engineering.
* Improving model evaluation and interpretation.
* Deploying the final model as a web application or API.

---

## 👨‍💻 Author

**Subash Dey**

Aspiring Data Analyst | Python | SQL | Excel | Power BI | Machine Learning
