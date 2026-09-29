# 🔥 Algerian Forest Fires — FWI Prediction

An end-to-end **Machine Learning + Flask web application** that predicts the **Fire Weather Index (FWI)** using meteorological and fire-weather data from the Algerian Forest Fires dataset.

The project covers the complete ML workflow — from **data cleaning, EDA, feature engineering, model comparison, and hyperparameter tuning to model deployment through Flask**.

## 📌 Overview

The **Fire Weather Index (FWI)** is a numerical indicator used to represent fire intensity based on weather and fuel-moisture conditions.

This project uses historical observations from two regions of Algeria:

* **Bejaia**
* **Sidi Bel-Abbes**

The application takes weather and fire-weather parameters as input and predicts the corresponding **FWI value** using a trained **Ridge Regression** model.

### Prediction Flow

```text
Meteorological & Fire-Weather Data
              ↓
        Data Preprocessing
              ↓
              EDA
              ↓
       Feature Engineering
              ↓
         Train-Test Split
              ↓
        Feature Scaling
              ↓
     Model Comparison
              ↓
       Ridge Regression
              ↓
       Saved ML Model
              ↓
        Flask Web App
              ↓
         User Input
              ↓
        Predicted FWI
```

## 🎯 What Does This Project Predict?

The project predicts:

**Fire Weather Index (FWI)**

FWI is a continuous numerical value, so this is a **Regression problem**, not a classification problem.

The model uses the following input features:

| Feature     | Description                      |
| ----------- | -------------------------------- |
| Temperature | Maximum daytime temperature (°C) |
| RH          | Relative Humidity (%)            |
| Ws          | Wind Speed (km/h)                |
| Rain        | Precipitation (mm)               |
| FFMC        | Fine Fuel Moisture Code          |
| DMC         | Duff Moisture Code               |
| ISI         | Initial Spread Index             |

**Target variable: `FWI`**

## 📊 Dataset

The dataset contains observations collected between **June 2012 and September 2012** from two regions in Algeria:

* Bejaia Region — Northeast Algeria
* Sidi Bel-Abbes Region — Northwest Algeria

The project uses a cleaned and preprocessed version of the Algerian Forest Fires dataset.

## 🧠 Machine Learning Workflow

### 1. Data Cleaning

The dataset was cleaned and prepared for machine learning by:

* Removing unwanted whitespace
* Resolving misplaced header rows
* Handling missing values
* Handling non-numeric values
* Converting columns to appropriate numeric types
* Preparing the final dataset for modelling

### 2. Exploratory Data Analysis

EDA was performed to understand:

* Feature distributions
* Relationships between variables
* Correlations
* Relationships between input features and FWI
* Multicollinearity between features

### 3. Feature Engineering

The relevant meteorological and fire-weather features were selected for model training.

Feature scaling was performed using **StandardScaler** before training the regression model.

### 4. Model Comparison

Multiple regression algorithms were evaluated:

* Linear Regression
* Ridge Regression
* Lasso Regression
* ElasticNet Regression

After comparison, **Ridge Regression** was selected for the final model.

Ridge Regression was useful because several FWI-related features have strong relationships with each other, creating potential multicollinearity.

### 5. Model Serialization

The trained model and scaler were saved using Pickle:

```text
models/
├── ridge.pkl
└── scaler.pkl
```

These saved artifacts are loaded by the Flask application during prediction.

## 🌐 Flask Web Application

The Machine Learning model is integrated into a Flask web application.

### Routes

#### `/`

Displays the landing/home page.

#### `/predictdata`

Displays the FWI prediction form.

#### `POST /predictdata`

The application:

1. Receives user input.
2. Converts the input into the required format.
3. Applies the saved `StandardScaler`.
4. Loads the trained Ridge Regression model.
5. Generates the predicted FWI.
6. Displays the prediction on the web page.

## 📁 Project Structure

```text
forestfire-main/
│
├── .ebextensions/
│   └── python.config
│
├── .vscode/
│   ├── extensions.json
│   ├── settings.json
│   └── tasks.json
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

## 🛠️ Tech Stack

### Programming Language

* Python

### Data Analysis

* Pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-Learn
* Linear Regression
* Ridge Regression
* Lasso Regression
* ElasticNet
* StandardScaler

### Web Development

* Flask
* Jinja2
* HTML
* CSS

### Deployment

* AWS Elastic Beanstalk

## ⚙️ Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/Samir-Shaw/forestfire-regression-project-.git
cd forestfire-regression-project-
```

### 2. Create a virtual environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS/Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## ▶️ Run the Application

Start the Flask application:

```bash
python application.py
```

The application will run at:

```text
http://127.0.0.1:5000/
```

Open the prediction interface at:

```text
http://127.0.0.1:5000/predictdata
```

## ☁️ AWS Elastic Beanstalk

The project includes configuration for deployment using **AWS Elastic Beanstalk**.

The WSGI entry point is configured as:

```text
application:application
```

The project includes:

```text
.ebextensions/
└── python.config
```

This configuration allows the Flask application to be deployed on an AWS Elastic Beanstalk Python environment.

## 🔑 Key Learning Outcomes

Through this project, the following concepts were implemented:

* End-to-end Machine Learning workflow
* Data cleaning and preprocessing
* Exploratory Data Analysis
* Feature engineering
* Correlation analysis
* Multicollinearity
* Feature scaling
* Regression model comparison
* Ridge Regression
* Model serialization
* Flask model deployment
* AWS Elastic Beanstalk deployment configuration

## 👨‍💻 Author

**Samir Shaw**

B.Tech — Computer Science & Engineering

GitHub: [Samir-Shaw](https://github.com/Samir-Shaw)

---

⭐ If you found this project useful, consider giving the repository a star.
