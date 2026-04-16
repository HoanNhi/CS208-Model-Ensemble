# CS208 – Model Ensemble for Breast Cancer Prediction

This repository contains **Assignment 4** for the *CS208 – Machine Learning* course at Fulbright University Vietnam. The project focuses on implementing and evaluating **ensemble learning methods** for breast cancer classification.

---

## Dataset

* **Name:** Breast Cancer Wisconsin Dataset
* **Source:** [https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)
* **Description:**
  A binary classification dataset used to predict whether a tumor is **malignant** or **benign**, based on 30 numerical features derived from cell nuclei.

---

## Usage

Install required dependencies:

```bash
pip install -r requirements.txt
```
Then run the notebook `210114-Assignment-4-SVM-Model-ensemble.ipynb`.

---

## Models Implemented

The project implements a Support Vector Machine (SVM) and multiple ensemble techniques:

### Single Model

* **SVM**

---

### Ensemble Methods

1. **Gradient Boosting**

   * Ensemble of decision trees trained sequentially

2. **XGBoost**

   * Optimized gradient boosting with regularization

3. **AdaBoost**

   * Sequential boosting using weighted samples and weak learners

4. **Bagging**

   * Ensemble of SVM models trained on bootstrap samples

5. **Stacking (Hard Voting)**

   * Combines predictions from:

     * Decision Tree
     * SVM
     * Random Forest
     * Logistic Regression

6. **Random Forest**

   * Ensemble of 10 decision trees using bootstrap aggregation and feature randomness

---

## Experimental Setup

* Most ensemble methods use **100 base models**
* Exceptions:

  * **Random Forest:** 10 trees
  * **Stacking:** fixed heterogeneous models

---

## Results

AdaBoost achieves the highest accuracy - with 0.97 weighted accuracy.

---

## Analysis

AdaBoost achieves the highest accuracy due to strong alignment between its learning mechanism and dataset characteristics:

* **Low dimensionality (~30 features)**: simple models suffice
* **Clean data (low noise)**: boosting does not overfit mislabeled points
* **Near-linear separability**: sequential weak learners approximate the boundary effectively
