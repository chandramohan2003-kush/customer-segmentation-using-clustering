# Customer Segmentation Using Unsupervised Learning

## 📌 Project Overview

This project focuses on **customer segmentation using unsupervised machine learning**.

The objective is to identify meaningful groups of customers based on their demographic characteristics, spending behavior, purchasing patterns, and interactions with marketing campaigns.

Three clustering approaches were explored:

- K-Means Clustering
- Gaussian Mixture Model (GMM)
- K-Means with Cosine Distance

The clustering models were evaluated primarily using **Silhouette Score** and **cluster size analysis**.

---

## 📊 Dataset

The dataset contains information about **2,240 retail customers**, including demographic information, product spending, purchasing channels, and marketing campaign responses.

After handling missing values, **2,216 customers** were used for clustering.

### Main Feature Categories

**Demographic Features**
- Education
- Age
- Income
- Living arrangement
- Number of children
- Family size
- Parent status

**Spending Features**
- Wine
- Fruits
- Meat
- Fish
- Sweets
- Gold products

**Purchase Behavior**
- Deal purchases
- Web purchases
- Catalog purchases
- Store purchases
- Web visits per month

**Marketing Campaign Features**
- Campaign acceptance indicators
- Complaint indicator
- Campaign response

---

# 🔍 Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the structure and distribution of the customer data.

The analysis included:

- Categorical variable distributions
- Numerical feature distributions
- Histograms with KDE
- Boxplots for outlier detection
- Skewness analysis
- Summary statistics

---

# Data Preprocessing

### 1. Removing Irrelevant Features

Identifier, date, and constant-value columns were removed because they do not provide useful information for customer segmentation.

### 2. Missing Value Handling

Rows containing missing values were removed.


### 3. Feature Engineering

Several meaningful customer-level features were created:

- `Age` from `Year_Birth`
- `Spent` from product-level spending variables
- `Living_With` from marital-status information
- `Children` from household child variables
- `Family_Size`
- `Is_Parent`

### 4. Encoding

Categorical variables were encoded using level encoder.

### 6. Feature Scaling

Features used for clustering were standardized using `StandardScaler`.

### 7. Principal Component Analysis

PCA was applied to reduce dimensionality while preserving the majority of the information contained in the original features.

---

# Clustering

## 2. Gaussian Mixture Model

A Gaussian Mixture Model was evaluated as a probabilistic alternative to K-Means.

Different numbers of components were investigated using **AIC and BIC**, followed by Silhouette Score evaluation.

---

## 1. K-Means Clustering

K-Means was initially applied to the PCA-transformed data.

Different values of \(K\) were evaluated using the Elbow Method and Silhouette Score.

---

## 3. K-Means with Cosine Distance

Because customer behavior may depend more on the **relative pattern of features** than their absolute magnitude, K-Means using cosine distance was also evaluated.

A custom cosine-distance-based K-Means implementation was used.