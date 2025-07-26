# Machine Learning Diabetes Classification Project

Machine Learning project for binary diabetes classification using clinical and demographic features.

## 📋 Project Overview

This repository contains a machine learning project developed for the Machine Learning course at Università degli Studi di Milano-Bicocca (Academic Year 2023/24), Professor: Elisabetta Fersini. The project implements and compares multiple ML algorithms to predict diabetes occurrence based on clinical indicators.

**Authors:** Lorenzo Megna, Lorenzo Molinari, Massimo Trippetta

## 🎯 Objective

Develop and compare robust binary classifiers to accurately classify individuals as diabetic (1) or non-diabetic (0) based on various clinical indicators and patient characteristics.

## 📊 Dataset

| Feature | Description | Range/Values |
|---------|-------------|--------------|
| **Gender** | Biological sex of the individual | Male / Female |
| **Age** | Patient age | 0-80 years |
| **Hypertension** | Hypertension presence | 0 (No) / 1 (Yes) |
| **Heart Disease** | Heart disease presence | 0 (No) / 1 (Yes) |
| **BMI** | Body Mass Index | 10.16-71.55 |
| **HbA1c Level** | Average blood sugar over 2-3 months | Continuous |
| **Blood Glucose Level** | Current blood glucose measurement | Continuous |
| **Diabetes** | Target variable | 0 (No) / 1 (Yes) |

**Note:** Smoking History was removed due to poor data quality (35,000 identical "no info" values).

### Dataset Statistics
- **Samples:** ~100,000
- **Class distribution:** 91.52% non-diabetic, 8.48% diabetic
- **Data balancing:** Applied SMOTE oversampling and stratified undersampling

## 🔬 Methodology

### Data Preprocessing
- **Exploratory Data Analysis:** Statistical summaries and visualizations
- **Data Balancing:** Stratified undersampling and SMOTE over-sampling
- **Feature Encoding:** Label encoding categorical variables
- **Splitting:** 65% training / 35% testing

### Models Implemented

#### 1. Decision Tree Classifier
- **Optimization:** Cost-Complexity Pruning (CCP Alpha)
- **Parameters:**
  - Criterion: Gini
  - Max Depth: 3
  - Splitter: Best
  - CCP Alpha: 0
- **Performance:** Balanced accuracy with high interpretability

#### 2. Neural Network
- **Architecture:**
  - Input Layer: 7 neurons (linear activation)
  - Hidden Layers: 5 neurons (tanh), 4 neurons (ReLU)
  - Output Layer: 2 neurons (sigmoid)
- **Training:** 20 epochs, early stopping
- **Results:**
  - Loss: 0.222
  - Sensitivity: 91%
  - Accuracy: 85%

#### 3. Support Vector Machine (SVM)
- **Kernel:** RBF
- **Optimization:** Grid Search for hyperparameters
- **Best Parameters:** C=9801, kernel='rbf'
- **Results:**
  - Accuracy: 84.7%
  - Sensitivity: 94.9%
  - AUC: 0.89

## 🏆 Results

The SVM with RBF kernel performed best, achieving:
- Highest sensitivity (94.9%)
- Overall accuracy (~84.7%)
- Best AUC (0.89)
