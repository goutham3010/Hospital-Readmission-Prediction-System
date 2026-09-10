# Hospital Readmission Prediction and Intelligent Patient Assistance System

## About the Project

This is my Software Engineering project for predicting whether a patient is likely to be readmitted to the hospital.

The project uses Machine Learning to predict hospital readmission risk. I am also using Explainable AI (SHAP) to understand why the model makes a particular prediction.

Later, I plan to add an LLM and RAG system so that the application can give easy-to-understand explanations and provide information based on hospital guidelines.

---

## Objectives

* Predict hospital readmission using Machine Learning.
* Compare different Machine Learning models.
* Find the best performing model.
* Improve the model using hyperparameter tuning.
* Explain predictions using SHAP.
* Build a simple web application using Streamlit.
* Add LLM-based explanations.
* Add RAG for retrieving information from medical/hospital documents.
* Provide useful patient assistance.

---

## Dataset

I am currently using a hospital readmission dataset with:

* 8,000 patient records
* 17 columns

Some of the important features are:

* Age
* Gender
* Region
* Primary Diagnosis
* Comorbidities Count
* Length of Stay
* Treatment Type
* Medications Count
* Follow-up Visits
* Previous Readmissions
* Insurance Type
* Discharge Disposition

The target column is:

```text
label
```

where:

```text
1 = Readmitted
0 = Not Readmitted
```

I removed `patient_id` because it is only an identifier.

I also removed `admission_date` from the initial model and excluded `readmission_risk_score` because it could cause data leakage if it is already derived from the target/risk information.

---

## Machine Learning Workflow

### Step 1 - Data Understanding ✅

I checked:

* Dataset shape
* Column names
* Data types
* Missing values
* Duplicate values
* Target distribution

### Step 2 - EDA ✅

I performed basic exploratory data analysis.

I checked:

* Target distribution
* Numerical feature distributions
* Categorical feature values
* Class imbalance
* Possible outliers and data issues

### Step 3 - Data Preparation ✅

I prepared the data for Machine Learning.

Main tasks:

* Removed unnecessary columns
* Separated features and target
* Identified numerical and categorical columns
* Scaled numerical features
* Applied One-Hot Encoding to categorical features
* Split data into training and testing sets
* Used `random_state=42`
* Used stratification
* Created a preprocessing pipeline using `ColumnTransformer` and `Pipeline`

### Step 4 - Model Training ✅

I trained three Machine Learning models:

1. Logistic Regression
2. Decision Tree
3. Random Forest

The purpose was to compare different models and select a suitable model for the project.

### Step 5 - Model Evaluation ✅

I evaluated the models using:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC
* Confusion Matrix
* Classification Report

Since the dataset has an imbalanced target, I also considered recall and F1-score instead of looking only at accuracy.

### Step 6 - Hyperparameter Tuning ✅

I used `GridSearchCV` to improve the Random Forest model.

I tested different hyperparameter combinations using 5-fold cross-validation.

The tuning was based on F1-score.

The best model obtained from the tuning process is stored as:

```python
final_model
```

### Step 7 - Explainable AI (SHAP) ✅

I used SHAP to understand the predictions made by the final Random Forest model.

SHAP helps identify:

* Which features are important
* Which features increase the predicted risk
* Which features decrease the predicted risk
* Why a particular patient received a certain prediction

This makes the Machine Learning model easier to understand.

---

## Current Status

### Completed

* [x] Data Understanding
* [x] Exploratory Data Analysis
* [x] Data Preparation
* [x] Train-Test Split
* [x] Model Training
* [x] Model Evaluation
* [x] Hyperparameter Tuning
* [x] SHAP Explainable AI

### Next Steps

* [ ] Step 8 - Save Final Model
* [ ] Step 9 - Build Streamlit Application
* [ ] Step 10 - Add LLM
* [ ] Step 11 - Add RAG
* [ ] Step 12 - Testing
* [ ] Deployment

---

## Technologies Used

### Currently Used

* Python
* Google Colab
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* SHAP

### Planned

* Streamlit
* SQLite
* OpenAI/Gemini API
* LangChain
* FAISS or ChromaDB
* Git and GitHub

---

## Basic Project Workflow

```text
Patient Dataset
      ↓
Data Understanding
      ↓
EDA
      ↓
Data Preparation
      ↓
Train/Test Split
      ↓
Model Training
      ↓
Model Evaluation
      ↓
Hyperparameter Tuning
      ↓
Final Random Forest Model
      ↓
SHAP Explanation
      ↓
Save Model
      ↓
Streamlit Application
      ↓
LLM
      ↓
RAG
      ↓
Patient Assistance
```

---

## Future Plan

After completing the Machine Learning and SHAP parts, I will save the final model and use it in a Streamlit application.

The LLM will be used to convert the ML prediction and SHAP explanation into simple natural-language explanations.

RAG will be added to retrieve relevant information from hospital or medical guideline documents and provide it as context to the LLM.

---

## Note

This project is being developed as an academic project for learning and demonstration purposes. The predictions and AI-generated information should not be considered a replacement for professional medical advice.
