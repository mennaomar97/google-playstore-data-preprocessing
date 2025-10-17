# 🧹 Google Play Store Apps — Data Preprocessing & EDA Project

## 📖 Project Overview

This project focuses on **data cleaning, preprocessing, and exploratory data analysis (EDA)**  
of the **Google Play Store Apps Dataset**.

The dataset contains details about thousands of apps — their category, ratings, size, installs, price, and more.  
Our goal is to **clean the dataset**, fix inconsistencies, handle missing values, detect outliers,  
and prepare it for meaningful analysis and visualization.

---

## 🎯 Objectives

1. Perform **comprehensive data cleaning and preprocessing**:

   - Handle missing values.
   - Fix incorrect or inconsistent data types.
   - Clean text-based columns (e.g., `Size`, `Installs`, `Price`).
   - Remove duplicate and redundant records.
   - Standardize formats (especially dates and version numbers).

2. Conduct **Exploratory Data Analysis (EDA)** to answer key business and analytical questions, such as:
   - What is the most expensive app on the Play Store?
   - Which genre has the highest number of apps?
   - What is the average size of free vs. paid apps?
   - How many apps have a rating higher than 4.7?
   - What’s Google’s estimated revenue from apps with 5M+ installs?

---

## 🧩 Dataset Information

| Column             | Description                                 |
| ------------------ | ------------------------------------------- |
| **App**            | Name of the application                     |
| **Category**       | Type/category of the app                    |
| **Rating**         | User rating (1–5)                           |
| **Reviews**        | Number of user reviews                      |
| **Size**           | App size (e.g. "12M", "Varies with device") |
| **Installs**       | Number of installs (e.g. "1,000,000+")      |
| **Type**           | Free or Paid                                |
| **Price**          | Price of the app (in $)                     |
| **Content Rating** | Target audience age group                   |
| **Genres**         | App genre(s)                                |
| **Last Updated**   | Date of last update                         |
| **Current Ver**    | Current version of the app                  |
| **Android Ver**    | Minimum Android version required            |

---

## 🧹 Data Cleaning Steps

### 1️⃣ Remove Duplicates

- Detected 1979 duplicate records.
- Removed exact duplicates using `drop_duplicates()`.
- Retained one record per app using highest number of `Reviews`.

### 2️⃣ Handle Missing Values

- Filled or removed missing values appropriately:
  - **Rating:** filled using median per category.
  - **Current Ver / Android Ver:** replaced invalid text with NaN.
  - **Size:** converted “Varies with device” to NaN.

### 3️⃣ Convert Data Types

- `Reviews`, `Installs`, and `Price` → numeric.
- `Last Updated` → datetime.
- `Size` → numeric (new column `SizeMB`).
- `Category`, `Type`, and `Content Rating` → categorical.

### 4️⃣ Feature Engineering

- Created new features:
  - `SizeMB` — converted all sizes to MB.
  - `Android_ver` — convert extracted numeric version from text.

### 5️⃣ Outlier Detection

- Detected outliers in `Rating`, `Reviews`, and `Price`.
- Removed unrealistic `Rating > 5` values.

---

## 📊 Exploratory Data Analysis (EDA)

- Distribution of app ratings.
- Average app size by category.
- Comparison between Free vs Paid apps.
- Correlation heatmap between `Rating`, `Reviews`, `Size`, and `Price`.
- Revenue estimation assuming 30% Google fee on paid app installs.

📈 Visualizations used:

- Bar charts
- Box plots
- Pie charts
- Heatmaps
- Histograms

---

## 🛠️ Tools & Libraries Used

- **Python 3**
- **Pandas** – data cleaning & manipulation
- **NumPy** – numerical operations
- **Matplotlib / Seaborn** – visualizations
- **scikit-learn** – encoding, scaling, preprocessing
- **Jupyter Notebook / VS Code** – development environment

---
