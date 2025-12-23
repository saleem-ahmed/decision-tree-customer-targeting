# 📊 Decision Tree–Based Customer Targeting for Deposit Campaign

## 📌 Project Overview

This project was completed for a **marketing analytics task** where the client wanted to identify **clear and interpretable rules** to help their marketing team target customers who are **most likely to make a deposit** in an upcoming campaign.

The dataset was provided by the client’s marketing department and contains information about customers who were previously contacted, including feedback from past campaigns (`poutcome`).

The client specifically requested a **Decision Tree–based solution** so that the output could be easily understood and used by non-technical marketing stakeholders.

---

## 🎯 Client Requirements

The client asked for:

* Analysis of customer deposit behavior
* Use of the **Decision Tree algorithm**
* Clear **if–then rules** instead of a black-box model
* Focus on customers who have previously made deposits
* Special attention to `poutcome` (previous campaign outcome)
* A **reproducible and documented solution**

---

## 📁 Dataset Description

* **Rows:** 11,162 customers
* **Target variable:** `deposit` (yes / no)
* **Key feature:** `poutcome` (outcome of previous campaign)

### Main columns include:

`age, job, marital, education, balance, housing, loan, campaign, pdays, previous, poutcome, deposit`

---

## ⚠️ Important Business Consideration

* The feature **`duration`** was removed from the analysis
* Reason: `duration` is only known *after* a marketing call and would cause **data leakage** for a future campaign

---

## 🛠️ Solution Approach

### Step 1: Data Loading

* Loaded the dataset into Python using Pandas
* Verified column structure and target variable

---

### Step 2: Data Cleaning & Preprocessing

* Converted `deposit` into a binary target (1 = yes, 0 = no)
* Handled missing and `unknown` values
* Removed leakage features
* One-hot encoded categorical variables
* Ensured the dataset was suitable for tree-based modeling

---

### Step 3: Exploratory Analysis

* Studied deposit rates across:

  * Previous campaign outcomes (`poutcome`)
  * Housing and loan status
  * Number of previous contacts
* Identified key behavioral patterns relevant to marketing

---

### Step 4: Decision Tree Modeling

* Used a **shallow Decision Tree** for interpretability
* Limited tree depth to avoid overfitting
* Balanced class weights to handle class imbalance
* Focused on extracting **business rules**, not just accuracy

---

### Step 5: Rule Extraction

* Extracted if–then rules directly from the trained Decision Tree
* Converted technical splits into **marketing-friendly rules**
* Identified:

  * High-priority customers
  * Medium-priority segments
  * Customers to exclude to save budget

---

## 📋 Key Rules Delivered to Client

| Rule | Description                                   | Action          |
| ---- | --------------------------------------------- | --------------- |
| R1   | Previous campaign outcome = success           | High priority   |
| R2   | No housing loan & low campaign count          | Target          |
| R3   | Housing loan & previous contacts              | Medium priority |
| R4   | Previous campaign failure & repeated contacts | Exclude         |

---

## 📈 Key Insights

* Previous campaign success (`poutcome = success`) is the **strongest predictor** of deposit conversion
* Repeatedly contacting failed customers reduces campaign efficiency
* Interpretable rules help marketing teams act quickly and confidently

---

## 📦 Deliverables

* ✔ Cleaned and processed dataset
* ✔ Interpretable Decision Tree model
* ✔ Extracted business rules
* ✔ Reproducible **Jupyter Notebook**
* ✔ Clear documentation for non-technical users

