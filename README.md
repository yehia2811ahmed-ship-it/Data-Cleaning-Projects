# 🏁 Final Project Report: Professional Data Cleaning & Structuring
**Project:** San Francisco Building Permits Dataset Optimization  
**Tools:** Python, Pandas, Regular Expressions (Regex), XlsxWriter

---

### 1️⃣ Project Overview
The objective was to transform a "dirty" and "sparse" dataset containing **198,900 records** of building permits into a high-quality, analysis-ready database. The original dataset suffered from significant missing values (**26.26% total missingness**) and unoptimized data types.

---

### 2️⃣ Data Cleaning Strategy & Actions Taken

#### 🛠️ Dimensionality Reduction (Noise Removal)
*   **Action:** Identified and dropped **7 columns** with over **95% missing values** (e.g., `TIDF Compliance`, `Site Permit`).
*   **Result:** Reduced data noise and improved processing speed by focusing on statistically significant attributes.

#### 🧠 Smart Imputation (Logical Filling)
Instead of simple deletion, I applied domain-specific logic to salvage data:
*   **Boolean Correction:** Filled `Fire Only Permit` nulls with **'N'**, converting a 90% empty column into a 100% complete feature.
*   **Cross-Column Validation:** 
    *   Filled missing `Proposed Stories` using the values from `Existing Stories`.
    *   Synchronized `Estimated Cost` and `Revised Cost` to ensure financial consistency.
*   **Statistical Imputation:** Used **Median** for financial costs and building stories to avoid bias from extreme outliers (e.g., skyscrapers vs. small houses).
*   **Categorical Integrity:** Labeled missing descriptions as **'Unknown'** to maintain sample size without compromising data accuracy.

#### 📅 Temporal & Structural Optimization
*   **Standardization:** Converted all date columns (6 columns) from generic strings to **Datetime objects**.
*   **Data Casting:** Cleaned and casted numerical counts into **Integers** for better readability and lower memory footprint.

---

### 3️⃣ Geographical Integrity
To ensure accuracy for spatial analysis, I performed a **Selective Row Drop** on records missing critical location data (`Zipcode` and `Location`). This resulted in a clean subset of **~197,000 high-integrity records**.

---

### 4️⃣ Final Deliverables
The project concluded with the generation of a **Professional Excel Dashboard File** featuring:
*   ✅ **Auto-fitted Columns:** For maximum readability.
*   ✅ **Header Formatting:** Color-coded and bolded for clarity.
*   ✅ **Active Filters:** Pre-enabled for immediate data exploration.
*   ✅ **Frozen Panes:** For seamless navigation through large records.

---

### 📈 Key Impact
*   **Data Health:** Improved from **73.74%** completeness to **100%** in core analytical columns.
*   **Usability:** The dataset is now fully prepared for **Time-Series Analysis**, **Financial Auditing**, and **Predictive Modeling**.
## 📊 Data Transformation (Before & After)


| Before Cleaning (Missing Values) | After Cleaning (Structured Data) |
| :---: | :---: |
| ![Before](before.png) | ![After](after.png) |
