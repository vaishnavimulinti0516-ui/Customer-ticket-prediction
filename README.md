# Customer Support Ticket Analysis & Satisfaction Prediction

## 📌 Project Overview

This project analyzes a **Customer Support Ticket Dataset** and builds machine learning classification models to predict the **Customer Satisfaction Rating (1–5)**.

The main objective is to identify whether customer and ticket-related information can help predict customer satisfaction and potentially flag tickets that may receive a low satisfaction rating.

---

## 🎯 Project Goal

The project focuses on:

* Exploring customer support ticket data
* Performing data cleaning
* Handling missing values
* Performing exploratory data analysis (EDA)
* Creating useful features
* Encoding categorical variables
* Scaling numerical features
* Training classification models
* Evaluating model performance
* Comparing different machine learning models
* Performing cross-validation
* Understanding feature importance

---

## 📂 Dataset

The dataset contains customer support ticket information such as:

* Customer information
* Product purchased
* Ticket type
* Ticket priority
* Ticket channel
* Ticket status
* Ticket description
* Ticket subject
* Resolution
* First response time
* Time to resolution
* Customer satisfaction rating

The original dataset contains approximately **8,469 rows and 17 columns**.

Only tickets with an available **Customer Satisfaction Rating** are used for supervised machine learning.

After filtering, approximately **2,769 rated tickets** are used for modeling.

---

## 🔍 Exploratory Data Analysis

The following EDA steps were performed:

* Dataset shape
* Column information
* Data types
* Descriptive statistics
* Missing-value analysis
* Duplicate-value checking
* Categorical and numerical column identification
* Customer age analysis
* Product analysis
* Response analysis
* Customer satisfaction rating distribution
* Class-balance visualization

---

## 🧹 Data Preprocessing

The preprocessing steps include:

1. Converting date columns into datetime format
2. Removing unnecessary identifier columns
3. Handling missing values
4. Creating customer age categories
5. Creating a response feature
6. Filtering tickets with valid satisfaction ratings
7. Extracting purchase month
8. Extracting purchase day of week
9. Removing unnecessary text and identifier columns
10. Frequency encoding `Product Purchased`
11. One-hot encoding categorical variables
12. Standard scaling for linear models

---

## 🛠️ Feature Engineering

Additional features were created, including:

### Type of Customer

Customers were grouped into:

* Young Customer
* Middle Age Customer
* Old Customer

### Response

A response feature was created:

* Yes → First response is available
* No → No response is available

### Purchase Features

From `Date of Purchase`:

* Purchase Month
* Purchase Day of Week

### Product Frequency

`Product Purchased` was frequency encoded based on how often each product appeared in the dataset.

### Resolution Sentiment

A simple lexicon-based sentiment score was calculated from the resolution text.

---

## 🤖 Machine Learning Models

Three classification models were implemented:

### 1. Logistic Regression

A linear classification model used as a baseline.

### 2. Random Forest

A tree-based ensemble classification algorithm.

Hyperparameter tuning was performed using `GridSearchCV`.

Parameters considered:

* `n_estimators`
* `max_depth`

### 3. SGD Classifier

`SGDClassifier` with logistic loss was used as a gradient-descent-based classifier.

---

## 📊 Evaluation Metrics

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Mean Absolute Error (MAE)
* Within ±1 Accuracy
* Confusion Matrix

Since customer satisfaction ratings are ordinal from 1 to 5, **MAE** and **Within ±1 Accuracy** were also considered.

---

## 🔄 Cross-Validation

A **5-fold Stratified Cross-Validation** approach was used to check whether the model results were stable across different training/validation splits.

The following metrics were compared:

* Cross-validation Accuracy
* Cross-validation F1 Score
* Mean
* Standard deviation

---

## 📈 Model Results

### Single 80/20 Test Split

| Model                  | Accuracy | F1 Score |   MAE | Within ±1 |
| ---------------------- | -------: | -------: | ----: | --------: |
| SGD (Gradient Descent) |    0.213 |    0.211 | 1.644 |     0.514 |
| Random Forest          |    0.193 |    0.190 | 1.551 |     0.540 |
| Logistic Regression    |    0.181 |    0.177 | 1.579 |     0.507 |

### 5-Fold Cross-Validation

| Model               |   CV Accuracy |         CV F1 |
| ------------------- | ------------: | ------------: |
| Logistic Regression | 0.214 ± 0.017 | 0.208 ± 0.016 |
| Random Forest       | 0.202 ± 0.012 | 0.200 ± 0.013 |
| SGD                 | 0.198 ± 0.016 | 0.186 ± 0.015 |

---

## 🧠 Key Findings

The models achieved approximately **20% accuracy**, which is close to the random-guess baseline for five balanced classes.

The results suggest that the available customer, product, and ticket attributes do not contain strong predictive information for the customer satisfaction rating in this dataset.

The resolution sentiment experiment also produced very little useful signal.

Therefore, the project demonstrates an important machine learning conclusion:

> A machine learning model may perform poorly when the available features do not contain meaningful information about the target variable.

---

## 🏗️ Project Workflow

```text
Dataset
   ↓
Data Loading
   ↓
Data Exploration
   ↓
Data Cleaning
   ↓
EDA
   ↓
Feature Engineering
   ↓
Target Selection
   ↓
Encoding
   ↓
Feature Scaling
   ↓
Train-Test Split
   ↓
Model Training
   ├── Logistic Regression
   ├── Random Forest
   └── SGD Classifier
   ↓
Model Evaluation
   ↓
Model Comparison
   ↓
5-Fold Cross-Validation
   ↓
Final Conclusion
```

---

## 💻 Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## 📁 Project Structure

```text
customer-support-satisfaction/
│
├── data/
│   └── customer_support_dataset.csv
│
├── notebooks/
│   └── customer_support_analysis.ipynb
│
├── README.md
│
└── requirements.txt
```

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Open the project folder

```bash
cd customer-support-satisfaction
```

### 3. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open the project notebook

Run the notebook cells from top to bottom.

---

## 👩‍💻 Author

**Vaishnavi**

B.Tech Graduate | Aspiring Data Analyst

### Skills Used in This Project

* Python
* Pandas
* NumPy
* Data Analysis
* Exploratory Data Analysis
* Machine Learning
* Scikit-learn
* Data Visualization


📁 customer-support-satisfaction
│
├── 📁 data
│   └── customer_support_dataset.csv
│
├── 📓 customer_support_analysis.ipynb
│
├── 📄 README.md
│
└── 📄 requirements.txt
