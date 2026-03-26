# Student Exam Performance Prediction (End-to-End ML Project)

# 🚀 Project Overview

This project is an end-to-end Machine Learning pipeline that predicts a student’s performance based on demographic and academic inputs. The application is deployed as a web app using Flask and hosted on Microsoft Azure App Services.

# 🧠 Introduction on Data

Predict student exam performance using features such as:

Gender
Race/Ethnicity
Parental Level of Education
Lunch Type
Test Preparation Course
Reading & Writing Scores

Target Variable : Maths Score

# 🛠️ Tech Stack

Programming Language: Python
Libraries: Pandas, NumPy, Scikit-learn
Model: Regression Model (CatBoost / Linear Regression / etc.)
Web Framework: Flask
Deployment: Microsoft Azure App Services
Version Control: Git & GitHub

# 📂 Project Structure
```
├── artifacts/
│   ├── model.pkl
│   ├── preprocessor.pkl
│
├── src/
│   ├── pipeline/
│   │   ├── predict_pipeline.py
│
├── templates/
│   ├── index.html
│   ├── home.html
│
├── application.py
├── requirements.txt
├── setup.py
└── README.md
```

# Azure Deployment Link

🔗 [Live Demo](https://gempriceprediction-ekd7dggvbmhtdqcx.canadacentral-01.azurewebsites.net/predictdata)

# Approach of the Project 

Approach for the project
1. Data Ingestion : In Data Ingestion phase the data is first read as csv.
Then the data is split into training and testing and saved as csv file.

2.Data Transformation : In this phase a ColumnTransformer Pipeline is created.
for Numeric Variables first SimpleImputer is applied with strategy median , then Standard Scaling is performed on numeric data.
for Categorical Variables SimpleImputer is applied with most frequent strategy, then ordinal encoding performed , after this data is scaled with Standard Scaler.
This preprocessor is saved as pickle file.

3.Model Training : In this phase base model is tested . The best model found was catboost regressor.
After this hyperparameter tuning is performed on catboost and knn model.
A final VotingRegressor is created which will combine prediction of catboost, xgboost and knn models.
This model is saved as pickle file.

4.Prediction Pipeline : This pipeline converts given data into dataframe and has various functions to load pickle files and predict the final results in python.

5. Flask App creation : Flask app is created with User Interface to predict the gemstone prices inside a Web Application.


