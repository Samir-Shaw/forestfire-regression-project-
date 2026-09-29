# 🔥 Forest Fire FWI Prediction

A Machine Learning project that predicts the **Fire Weather Index (FWI)** using meteorological and fire-weather features from the Algerian Forest Fires dataset.

The project includes data cleaning, exploratory data analysis, feature engineering, model comparison, Ridge Regression, and a Flask web application for making predictions.

---

## 📌 Project Overview

Forest fires are influenced by several weather and environmental conditions. This project uses historical fire-weather data to predict the **Fire Weather Index (FWI)**, which is a continuous numerical value.

This is a **Regression problem** because the target variable, FWI, is numerical.

### 🎯 Target

**Fire Weather Index (FWI)**

### 📥 Input Features

* Temperature
* Relative Humidity (RH)
* Wind Speed (Ws)
* Rain
* Fine Fuel Moisture Code (FFMC)
* Duff Moisture Code (DMC)
* Initial Spread Index (ISI)

---

## 📊 Dataset

The project uses the **Algerian Forest Fires Dataset**.

The dataset contains observations collected between **June 2012 and September 2012** from two regions of Algeria:

* Bejaia Region
* Sidi Bel-Abbes Region

The original dataset was cleaned and prepared before model training.

---

## 🔄 Machine Learning Workflow

```text
Raw Dataset
     ↓
Data Cleaning
     ↓
Exploratory Data Analysis
     ↓
Feature Engineering
     ↓
Correlation / Multicollinearity Analysis
     ↓
Train-Test Split
     ↓
Feature Scaling
     ↓
Model Training
     ↓
Model Comparison
     ↓
Ridge Regression
     ↓
Model & Scaler Saved
     ↓
Flask Web Application
     ↓
FWI Prediction
```

---

## 🧹 Data Preprocessing

The dataset was prepared through several preprocessing steps:

* Removed unnecessary whitespace
* Handled misplaced headers
* Converted columns to appropriate data types
* Handled missing and non-numeric values
* Performed exploratory data analysis
* Checked feature correlations
* Analyzed multicollinearity
* Selected relevant features
* Applied feature scaling using `StandardScaler`

---

## 🤖 Models Used

The following regression algorithms were explored and compared:

* Linear Regression
* Ridge Regression
* Lasso Regression
* ElasticNet Regression

Because of multicollinearity among some features, **Ridge Regression** was selected for the final model.

The trained model and scaler are saved using Python's `pickle` functionality:

```text
models/
├── ridge.pkl
└── scaler.pkl
```

---

## 🌐 Flask Web Application

A Flask web application was created to allow users to enter the required weather parameters and receive an FWI prediction.

### Application Flow

```text
User enters weather data
        ↓
Flask receives input
        ↓
Input is converted to numerical values
        ↓
StandardScaler transforms the input
        ↓
Ridge Regression model predicts FWI
        ↓
Predicted FWI displayed to user
```

### Flask Routes

| Route          | Method | Purpose                          |
| -------------- | ------ | -------------------------------- |
| `/`            | GET    | Displays the home page           |
| `/predictdata` | GET    | Displays prediction form         |
| `/predictdata` | POST   | Processes input and predicts FWI |

---

## 📁 Project Structure

```text
forestfire-main/
│
├── .ebextensions/
│   └── python.config
│
├── .vscode/
│
├── dataset/
│   └── Algerian_forest_fires_cleaned_dataset.csv
│
├── models/
│   ├── ridge.pkl
│   └── scaler.pkl
│
├── notebooks/
│   ├── 2.0-EDA And FE Algerian Forest Fires.ipynb
│   └── 3.0-Model Training.ipynb
│
├── templates/
│   ├── home.html
│   └── index.html
│
├── application.py
├── requirements.txt
└── README.md
```

---

## 🛠️ Technologies Used

### Programming Language

* Python

### Machine Learning

* Scikit-learn
* NumPy
* Pandas

### Data Analysis & Visualization

* Matplotlib
* Seaborn

### Web Framework

* Flask

### Model Persistence

* Pickle

### Development

* Jupyter Notebook
* VS Code
* Git & GitHub

---

## 🚀 Run the Project Locally

### 1. Clone the repository

```bash
git clone https://github.com/Samir-Shaw/forestfire-regression-project-.git
cd forestfire-regression-project-
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the virtual environment

#### Windows

```bash
venv\Scripts\activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Flask application

```bash
python application.py
```

### 6. Open in browser

```text
http://127.0.0.1:5000/
```

---

## 📌 Deployment

The project is currently configured as a Flask application and can be deployed to a cloud hosting platform in the future.

**Cloud deployment has not been completed yet.**

The `.ebextensions/python.config` file is included as deployment configuration for potential **AWS Elastic Beanstalk** deployment, but the application is **not currently deployed on AWS**.

---

## 🎓 What I Learned

Through this project, I worked on:

* Data cleaning and preprocessing
* Exploratory Data Analysis (EDA)
* Feature engineering
* Correlation analysis
* Multicollinearity
* Feature scaling
* Regression algorithms
* Ridge, Lasso and ElasticNet
* Model comparison
* Saving trained ML models
* Building a Flask ML application
* Connecting a trained ML model with a web interface
* Git and GitHub project management

---

## 👨‍💻 Author

**Samir Shaw**

B.Tech Computer Science & Engineering

GitHub: `Samir-Shaw`

---

## ⭐ Project Goal

The main goal of this project is to demonstrate an end-to-end **Machine Learning workflow**, starting from raw data preprocessing and analysis to model training and integration with a Flask web application for real-time FWI prediction.
