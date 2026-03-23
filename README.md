📊 COVID-19 Data Analysis Project
📌 Project Description

This project focuses on analyzing a medical dataset related to COVID-19 (SARS-CoV-2).
The goal is to explore, clean, and analyze the data to extract meaningful insights and prepare for future machine learning tasks.

📁 Dataset
File: dataset.xlsx
Contains patient medical data including:
Blood test results
Virus detection
COVID-19 test results (target)
🧪 Project Overview
🔹 Part 1: Initialisation et Analyse de Forme
Load the dataset from dataset.xlsx
Create a copy named df
Display:
First 5 rows (head())
Dataset shape (shape)
Data types distribution (dtypes.value_counts())
🔹 Part 2: Gestion des valeurs manquantes (NaN)

Visualize missing values using heatmap:

sns.heatmap(df.isna())
Analyze missing data structure
Compute percentage of NaN per column
Data cleaning:
Remove columns with more than 90% missing values
Remove Patient ID column
Check updated dataset shape
🔹 Part 3: Analyse de la Target
Target variable: SARS-Cov-2 exam result

Display distribution:

df['SARS-Cov-2 exam result'].value_counts(normalize=True)
Determine:
Is the dataset balanced?
Which performance metric to prioritize (e.g., F1-score, recall)
🔹 Part 4: Analyse des variables
1. Data Separation
Float columns → blood variables
Object columns → viral variables
2. Distribution Analysis

Plot distributions:

sns.distplot(df[col])
Check if variables are standardized
3. Relationship with Target
Plot distributions by COVID result (positive/negative)
Identify variables that separate classes:
Platelets
Leukocytes
Others...
🔹 Part 5: Variables Catégorielles

Use cross-tabulation:

pd.crosstab(df['SARS-Cov-2 exam result'], df['Influenza A'])
Analyze co-infections
New Feature

Create a column:

df['est_malade'] = ...
Compare with COVID target
🔹 Part 6: Corrélations et Tests Statistiques
1. Correlation Matrix
sns.heatmap(df.corr())
Identify highly correlated variables
2. Statistical Test (Student T-test)
from scipy.stats import ttest_ind
Compare means between:
COVID positive
COVID negative
3. Significant Variables

Select variables with:

p-value < 0.05
Validate findings from visual analysis
🛠️ Technologies Used
Python 🐍
Pandas
NumPy
Matplotlib
Seaborn
SciPy
🎯 Objectives
Understand data structure
Handle missing values
Perform exploratory data analysis (EDA)
Identify important features
Prepare for machine learning modeling
🚀 Future Work
Build classification models (Logistic Regression, Random Forest, etc.)
Evaluate model performance
Feature engineering and selection
