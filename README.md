# Python-Data-SLicing-Indexing
# 🎓 Student Data Analysis – Python & Pandas (Day 3)

This repository contains a Python-based data analysis exercise completed in Google Colab. The project explores a student dataset using pandas, showcasing data cleaning, exploration, filtering, and statistical insight generation.

---

## 📌 Project Overview

**Platform:** Google Colab  
**Language:** Python  
**Library:** pandas  
**Dataset:** `student.xlsx` (35 records, 5 columns)  
**Focus Areas:**  
- Data loading and inspection  
- Column selection and slicing  
- Boolean masking and conditional filtering  
- Statistical analysis and aggregation  
- Indexing with `loc` and `iloc`

---

## 🧪 Functions & Logic Summary

### 📥 Data Import & Inspection
- `pd.read_excel()` – loads Excel file into a DataFrame  
- `df.head()`, `df.tail()` – previews top and bottom rows  
- `df.info()`, `df.describe()` – inspects structure and summary stats  
- `df.dtypes`, `df.isnull().sum()` – checks data types and missing values

### 🔍 Column Selection & Slicing
- `df[['name', 'class', 'mark', 'gender']]` – selects multiple columns  
- `df.loc[0:5, 'name']`, `df.loc[0:14, 'mark'].mean()` – label-based slicing  
- `df.iloc[[1,4,5], [1,2]]` – position-based slicing

### 📊 Statistical Analysis
- `df['mark'].mean()` – overall average mark  
- `df['mark'].max()`, `df['mark'].min()` – highest and lowest marks  
- Grouped averages:
  - `df[df['gender'] == 'female']['mark'].mean()`  
  - `df[df['gender'] == 'male']['mark'].mean()`  
  - `df[df['class'] == 'Five']['mark'].mean()`  
  - `df[(df['class'] == 'Six') & (df['gender'] == 'male')]['mark'].mean()`

### 🧠 Boolean Masking & Filtering
- `df[df['mark'] > 90]`, `df[df['mark'] < 50]` – filter by mark  
- `df[df['gender'] == 'female']`, `df[df['class'] == 'Four']` – filter by category  
- Combined filters:
  - `df[(df['id'] > 20) & (df['id'] < 30)]`  
  - `df[(df['class'] == 'Four') & (df['gender'] == 'male')]`  
  - `df[(df['gender'] == 'female') & (df['mark'] >= 74)]`

### 📈 Advanced Filtering & Sorting
- Compare female marks to overall average:
  - `df.loc[(df['gender'] == 'female') & (df['mark'] > average), ['name', 'mark', 'gender']]`  
  - `.sort_values(by='mark', ascending=False)` – rank by performance

### 📊 Aggregation & Counts
- `df['gender'].value_counts()` – count of male vs female students  
- `df['class'].value_counts()` – student distribution by class  
- `df['mark'].value_counts()` – frequency of each mark

---

## 💼 Skills Demonstrated

- ✅ Data loading and inspection with pandas  
- ✅ Column selection and slicing using `loc` and `iloc`  
- ✅ Boolean masking and conditional filtering  
- ✅ Statistical analysis and aggregation  
- ✅ Sorting and ranking based on conditions  
- ✅ Exploratory data analysis (EDA) techniques

---

## 📷 Sample Output

```text
Average mark for first 15 students: 75.53  
Average mark (female): 77.31  
Average mark (male): 71.59  
Highest mark: 96  
Lowest mark: 18  
Female students with above-average marks:
| name     | mark | gender |
|----------|------|--------|
| Ayesha   | 96   | female |
| Fatima   | 88   | female |
...
