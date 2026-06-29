# Titanic Dataset — Data Cleaning

A hands-on data cleaning exercise using the Titanic dataset, covering common real-world data quality issues: missing values, duplicates, incorrect data types, outliers, and inconsistent formats.

## 📌 Objective

Practice the end-to-end data cleaning workflow:
- Assess data quality
- Handle missing values
- Detect and remove duplicates
- Identify and treat outliers
- Scale/normalize features for downstream ML use

## 🗂 Dataset

[Titanic-Dataset.csv](https://media.geeksforgeeks.org/wp-content/uploads/20250114171103408125/Titanic-Dataset.csv) — 891 rows, 12 columns (PassengerId, Survived, Pclass, Name, Sex, Age, SibSp, Parch, Ticket, Fare, Cabin, Embarked).

## 🛠 Steps Performed

1. **Load & inspect data** — `df.info()`, `df.head()`
2. **Check duplicates** — `df.duplicated().sum()` → 0 duplicates found
3. **Identify column types** — separated categorical vs numerical columns
4. **Calculate missing values** — found `Cabin` ~77% missing, `Age` ~20% missing, `Embarked` ~0.2% missing
5. **Handle missing data:**
   - Dropped `Name`, `Ticket`, `Cabin` (irrelevant or too many missing values)
   - Dropped rows with missing `Embarked` (very few)
   - Imputed missing `Age` values with column mean
6. **Detect outliers** — visualized `Age` with a box plot
7. **Remove outliers** — filtered values outside `mean ± 2*std`, repeated after re-imputation
8. **Feature/target split** — `X` (features) and `y` (`Survived`)
9. **Scale features** — applied `MinMaxScaler` to normalize numeric columns to [0, 1]

## 📊 Key Findings

- No duplicate rows in the raw dataset
- `Cabin` had too much missing data to reliably impute → dropped
- `Age` had a moderate number of outliers (very old passengers) → removed using the 2-std rule
- After cleaning, dataset was reduced from 891 rows to **[X] rows** (update with your final count)

## 🧰 Tools Used

- Python (Google Colab)
- pandas, numpy
- matplotlib (box plots)
- scikit-learn (MinMaxScaler)

## 📁 Files

- `Data_Cleaning.ipynb` — full notebook with code, outputs, and comments

## 🎯 What I Learned

- Difference between dropping vs imputing missing values, and when to choose each
- How to detect outliers visually (box plot) and statistically (mean ± std)
- Common pandas pitfalls: `inplace=True` + reassignment, copy vs view warnings
- Difference between database normalization and ML feature normalization

## 🔗 Reference

Exercise based on [GeeksforGeeks — Data Cleaning](https://www.geeksforgeeks.org/data-analysis/data-cleaning-introduction/)
