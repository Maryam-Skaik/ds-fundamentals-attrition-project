# 🎯 Employee Attrition Analysis  

This project presents a full data cleaning and exploratory data analysis (EDA) workflow on an Employee Attrition dataset.  
The goal is to help HR executives understand the key factors influencing employee turnover.

---

## 📌 Project Objective

Analyze employee data to identify patterns and trends related to **attrition (employee leaving the company)** using Python.

---

## 📂 Dataset Overview

The dataset includes employee information such as:

- Demographics (Age, Gender, MaritalStatus)
- Job-related features (Department, JobRole, JobLevel)
- Satisfaction metrics (Job, Environment, Relationship, Work-Life Balance)
- Compensation (HourlyRate, DailyRate, YearlyRate, Salary Hike)
- Work history (YearsAtCompany, TotalWorkingYears, etc.)

**Target Variable:**  
- `Attrition` → Yes / No

---

## 🧹 Data Cleaning Process

The following steps were applied to prepare the dataset:

- Removed duplicate rows  
- Fixed incorrect data types (`HourlyRate`, `YearsAtCompany`)  
- Handled missing values:
  - `Gender` filled with placeholder `MISSING`  
- Checked and ensured consistency in categorical values  
- Handled invalid data:
  - Replaced unrealistic `Age` values (e.g., 578) with median  
- Converted ordinal features to ordered categorical:
  - (e.g., `JobSatisfaction`, `WorkLifeBalance`, etc.)  
- Identified constant features:
  - `EmployeeCount`, `StandardHours`, `Over18`  

---

## 📊 Exploratory Data Analysis (EDA)

### 🔹 Univariate Analysis

Two types of visualizations were used:

- **Categorical Features → Countplots**
  - Distribution of features like `Department`, `JobRole`, `OverTime`
- **Numeric Features → Histogram + Boxplot**
  - Distribution, skewness, and outliers (e.g., `Age`, `YearsAtCompany`)

---

### 🔹 Multivariate Analysis

Two types of relationships were explored:

#### 1. Categorical vs Target (Attrition)
- Barplots showing **proportion of employees leaving**
- Example insights:
  - Employees working overtime are more likely to leave  
  - Sales roles show higher attrition  

#### 2. Numeric vs Target
- Boxplots comparing distributions between `Attrition = Yes/No`
- Example:
  - Employees with fewer years in company are more likely to leave  

#### 3. Correlation Heatmap
- Used to detect relationships between numeric features  
- Helped identify **redundant features and multicollinearity**

---

## 📌 Key Insights

- **Attrition is imbalanced**: ~84% stay, ~16% leave  

### 🔥 Strong Drivers of Attrition
- OverTime → employees working overtime leave more  
- JobSatisfaction & WorkLifeBalance → low values increase leaving  
- JobRole & Department → Sales roles/departments have higher attrition  
- BusinessTravel → frequent travel increases attrition  

### 📉 Behavioral Patterns
- Younger employees leave more often  
- Employees with fewer years in company or role are more likely to leave  
- Manager relationship plays a key role in retention  

### 💰 Unexpected Finding
- `PercentSalaryHike` has little impact on attrition  

---

## 🔗 Feature Relationships (Heatmap Insights)

- Strong redundancy:
  - `HourlyRate`, `DailyRate`, `YearlyRate` → identical information  
- Experience-related features are highly correlated:
  - `YearsAtCompany`, `YearsInCurrentRole`, `YearsWithCurrManager`  
- Indicates potential **multicollinearity**

---

## 🧠 Modeling Recommendations

- Drop constant features (no predictive value)  
- Remove redundant features (e.g., salary columns)  
- Handle multicollinearity among experience-related variables  
- Focus on strong predictors:
  - `OverTime`, `JobSatisfaction`, `WorkLifeBalance`, `YearsWithCurrManager`  

---

## 🛠️ Tools Used

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  

---

## 📚 References

- Pandas Documentation  
- Seaborn Documentation  
- Crosstab explanation:  
  https://medium.com/@whyamit404/understanding-pandas-crosstab-with-simple-examples-90cf6ea5a9a1
