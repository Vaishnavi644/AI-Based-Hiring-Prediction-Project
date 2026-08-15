# 🤖 AI-Based Hiring Prediction System

## 📌 Project Overview

The **AI-Based Hiring Prediction System** is a Machine Learning project developed to predict whether a candidate is likely to be **Hired or Rejected** based on resume-related information.

The project was developed as part of the **3Skill AI/ML Internship Program (June 2026 – August 2026)** using a synthetic recruitment dataset provided during the internship.

The system follows an end-to-end Machine Learning workflow, including:

* Exploratory Data Analysis (EDA)
* Data preprocessing
* Feature engineering
* Model training
* Model evaluation
* Model comparison
* Hyperparameter tuning
* Feature importance analysis

The project demonstrates how Machine Learning can be applied to support automated candidate screening and data-driven recruitment decisions.

---

## 🎯 Objectives

The main objective of this project is to develop a Machine Learning system that predicts a candidate's hiring outcome based on resume-related information.

### Specific Objectives

* Analyze and understand the recruitment dataset.
* Perform Exploratory Data Analysis (EDA).
* Identify and handle missing values.
* Remove unnecessary features.
* Encode categorical variables for Machine Learning.
* Split the dataset into training and testing sets.
* Build and compare multiple classification models.
* Evaluate models using standard classification metrics.
* Select the best-performing model.
* Optimize the selected model using `GridSearchCV`.
* Analyze feature importance to understand the factors influencing hiring predictions.

---

## 📊 Dataset

The dataset was provided by **3Skill** as part of the internship program.

It is a **synthetic recruitment/resume screening dataset** designed to simulate a real-world hiring scenario.

### Dataset Information

| Attribute       | Details                            |
| --------------- | ---------------------------------- |
| Dataset Source  | 3Skill Internship Program          |
| Dataset Type    | Synthetic Resume Screening Dataset |
| Total Records   | 1,000                              |
| Total Features  | 11 Columns                         |
| Target Variable | Recruiter Decision                 |
| Target Classes  | Hire / Reject                      |
| Missing Values  | Present in Certifications          |

### Features

The dataset contains information related to:

* Resume ID
* Candidate Name
* Skills
* Experience (Years)
* Education
* Certifications
* Job Role
* Recruiter Decision
* Salary Expectation ($)
* Projects Count
* AI Score (0–100)

The target variable is **Recruiter Decision**.

For Machine Learning:

* `Hire → 0`
* `Reject → 1`

---

## 🔄 Project Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
Exploratory Data Analysis (EDA)
   ↓
Data Preprocessing
   ↓
Feature Encoding
   ↓
Train-Test Split
   ↓
Model Training
   ↓
Model Evaluation
   ↓
Model Comparison
   ↓
Best Model Selection
   ↓
Hyperparameter Tuning
   ↓
Feature Importance Analysis
   ↓
Hiring Prediction
```

---

## 🔍 Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the structure and quality of the dataset.

The analysis included:

* Dataset information
* Summary statistics
* Missing-value analysis
* Duplicate-value checking
* Numerical feature distributions
* Categorical feature distributions
* Hiring outcome distribution
* Analysis of Skills, Education, Certifications, and Job Role

The `info()`, `describe()`, and `isnull().sum()` functions were used during the analysis.

The analysis showed that missing values were present only in the **Certifications** column.

---

## 🧹 Data Preprocessing

Several preprocessing techniques were applied before model training.

### 1. Handling Missing Values

Missing values in the `Certifications` column were replaced with:

```text
No Certification
```

### 2. Removing Unnecessary Columns

The following columns were removed:

* `Resume_ID`
* `Name`

These columns were unique identifiers and did not contribute meaningfully to the hiring prediction task.

### 3. Encoding Categorical Variables

Categorical variables were converted into numerical values using **Label Encoding**.

Encoded features included:

* Skills
* Education
* Certifications
* Job Role
* Recruiter Decision

### 4. Preventing Data Leakage

The `AI Score (0–100)` feature was excluded from model training because it had an almost direct relationship with the target variable.

Removing this feature helped prevent data leakage and allowed the models to learn from meaningful candidate attributes instead.

### 5. Train-Test Split

The processed dataset was divided into:

* **80% Training Data**
* **20% Testing Data**

A **stratified train-test split** was used to maintain the class distribution.

---

## 🤖 Machine Learning Models

Multiple classification algorithms were implemented and compared.

### 1. Logistic Regression

Logistic Regression was implemented as a baseline classification model.

Two versions were evaluated:

* Logistic Regression without scaling
* Logistic Regression with StandardScaler

### 2. K-Nearest Neighbors (KNN)

KNN was used as a distance-based classification model.

The value of:

```text
K = 5
```

was used during model training.

Since KNN is sensitive to feature scales, `StandardScaler` was applied.

### 3. Decision Tree

A Decision Tree classifier was implemented to classify candidates based on their resume attributes.

Decision Tree does not require feature scaling because it makes decisions using feature thresholds.

The Decision Tree achieved the best overall performance among the evaluated models and was selected for further optimization.

---

## 📏 Model Evaluation

The models were evaluated using the following metrics:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Classification Report

These metrics were used to compare the performance of the different classification models and identify the most suitable model for the hiring prediction task.

---

## ⚙️ Hyperparameter Tuning

After comparing the models, the **Decision Tree** was selected for further optimization.

`GridSearchCV` was used to identify a suitable combination of hyperparameters.

The parameters explored included:

* Criterion (`Gini` / `Entropy`)
* Maximum Depth
* Minimum Samples Split
* Minimum Samples Leaf

The best parameter combination identified through GridSearchCV was then used to train the final optimized Decision Tree model.

---

## 📊 Feature Importance Analysis

Feature importance analysis was performed using the Decision Tree model to understand which resume-related attributes contributed most to the hiring prediction.

The analysis focused on meaningful candidate attributes such as:

* Experience
* Education
* Skills
* Certifications
* Projects
* Salary Expectation
* Job Role

The `AI Score` feature was excluded to prevent data leakage and ensure that the model learned from genuine resume-related information.

Feature importance analysis also improved the interpretability of the model by showing which attributes contributed more strongly to its predictions.

---

## 🏆 Best Model

After comparing the implemented classification models, the **Decision Tree** demonstrated the best overall classification performance.

Therefore, the Decision Tree was selected and further optimized using **GridSearchCV**.

The optimized model was evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Classification Report

---

## 💻 Technologies & Tools

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Scikit-learn**
* **Google Colab**
* **Machine Learning**
* **Data Analysis & Visualization**

### Scikit-learn Techniques Used

* Logistic Regression
* K-Nearest Neighbors
* Decision Tree
* StandardScaler
* Label Encoding
* Train-Test Split
* GridSearchCV
* Classification Metrics

---

## 📓 Project Notebook

The complete implementation of the project is available in the Google Colab/Jupyter Notebook included in this repository.

**Notebook:**

`AI_Based_Hiring_Prediction_System.ipynb`

---

## 📄 Project Report

A detailed project report is included in this repository covering:

* Introduction
* Problem Statement
* Objectives
* Dataset Description
* Methodology
* Exploratory Data Analysis
* Data Preprocessing
* Model Building
* Model Comparison
* Hyperparameter Tuning
* Feature Importance Analysis
* Conclusion
* Future Scope

**Report:**

`AI-Based Hiring Prediction System Project Report.pdf`

---

## 🚀 Future Scope

The project can be further improved by incorporating advanced Machine Learning and Natural Language Processing techniques.

Possible future enhancements include:

* Using **TF-IDF, Word2Vec, or BERT embeddings** for resume text analysis.
* Using `MultiLabelBinarizer` or One-Hot Encoding for better representation of individual skills.
* Training models on real-world recruitment datasets.
* Developing a web application using **Flask, Django, or Streamlit**.
* Allowing recruiters to upload resumes and receive hiring predictions.
* Integrating the system with Applicant Tracking Systems (ATS).
* Exploring advanced models such as Random Forest, XGBoost, and LightGBM.

---

## 🎓 Internship

This project was developed as part of the:

**3Skill AI/ML Internship Program**
**Duration:** June 2026 – August 2026

The project provided practical experience in applying Machine Learning techniques to a recruitment-related problem and understanding the complete ML workflow from data preprocessing to model evaluation and optimization.

---

## 👩‍💻 Author

**Vaishnavi Sharma**

AI/ML Intern
3Skill AI/ML Internship Program

---

## 📚 References

* [Scikit-learn Documentation](https://scikit-learn.org/)
* [Pandas Documentation](https://pandas.pydata.org/)
* [NumPy Documentation](https://numpy.org/)
* [Matplotlib Documentation](https://matplotlib.org/)
* [Google Colaboratory Documentation](https://colab.research.google.com/)
* 3Skill Internship Program – AI-Based Hiring Prediction Dataset

