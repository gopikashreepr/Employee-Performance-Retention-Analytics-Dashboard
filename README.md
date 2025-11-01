# 🧩 Employee Performance & Retention Analytics Dashboard  
**Domain:** HR Analytics  
**Tools:** Power BI | Python | SQL | DAX  

---

## 📘 Project Overview

This project analyzes employee performance, satisfaction, and attrition patterns using data-driven insights and machine learning.  
It combines **Python-based predictive modeling** with **Power BI interactive dashboards** to help HR teams identify employees who are at high risk of attrition or may need upskilling.

The project is built using the **IBM HR Analytics Employee Attrition & Performance dataset**.

---

## 🎯 Objectives
- Understand factors influencing employee attrition and performance.  
- Predict the likelihood of an employee leaving the organization.  
- Provide HR decision-makers with interactive, data-driven insights.  
- Design a real-world styled analytics solution similar to systems used in companies like **Capgemini** and **IBM**.

---

## 🧠 Tech Stack

| Tool | Purpose |
|------|----------|
| **Python (Pandas, NumPy, Scikit-learn)** | Data cleaning, preprocessing, predictive modeling |
| **Power BI** | Data visualization and interactive dashboard creation |
| **SQL** | Data querying and transformation |
| **DAX** | KPI and calculated measure creation |

---

## 🧾 Dataset
**Source:** [IBM HR Analytics Employee Attrition & Performance (Kaggle)](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-employee-attrition-performance)  
**Records:** 1470 employees  
**Key Columns:** Age, Department, Education, Gender, JobRole, MonthlyIncome, PerformanceRating, Attrition  

---

## 🧹 Python Notebook
**File:** `code.ipynb`  
Tasks performed:
- Data import and inspection  
- Handling missing values & encoding categorical columns  
- Exploratory Data Analysis (EDA)  
- Building and evaluating ML models (Logistic Regression / Random Forest)  
- Generating predictions and exporting to CSV (`employee_attrition_results.csv`)  

**Output:**  
Predicted attrition values integrated into Power BI for visualization.  

---

## 📊 Power BI Dashboard

**File:** `IBM HR Analytics Employee Attrition & Performance.pbix`

### 🔹 Page 1 – Overview
- KPIs: Total Employees, Attrition Rate (%), Avg Monthly Income, Avg Satisfaction Score
- Charts: Department vs Attrition (Bar), Gender-wise Attrition (Clustered Column), Attrition by Marital Status (Donut), Predicted Attrition Trend by Tenure (Line)

### 🔹 Page 2 – Performance & Satisfaction Insights
- KPIs: Avg Job Satisfaction, Avg Environment Satisfaction, Avg Work-Life Balance, Promotion Rate (%)
- Charts: Department vs Job Satisfaction (Bar), Performance Rating vs Tenure (Line), Monthly Income vs Performance Rating (Scatter), Attrition by Marital Status (TreeMap) 

### 🔹 Page 3 – Predictive Attrition (AI Insights)
- KPIs: Avg Predicted Attrition, High-Risk Employee Count
- Charts: Employee Risk Table (EmployeeNumber | Department | Predicted Attrition | Risk Level), High-Risk Employee Count by Department (Bar), Attrition by Age (Line)
- Filters: Department, JobRole, Gender, Age Group

---

## 🧮 Key DAX Measures

```DAX
Attrition Rate (%) =
DIVIDE(
    CALCULATE(COUNTROWS(employee_attrition_results), employee_attrition_results[Attrition] = "Yes"),
    COUNTROWS(employee_attrition_results)
) * 100

Risk Level =
SWITCH(
    TRUE(),
    employee_attrition_results[Attrition_Predicted] = 1, "High",
    employee_attrition_results[Attrition_Predicted] = 0, "Low"
)

Age Group =
SWITCH(
    TRUE(),
    employee_attrition_results[Age] < 30, "Under 30",
    employee_attrition_results[Age] < 40, "30–39",
    employee_attrition_results[Age] < 50, "40–49",
    "50+"
)

---

## 🌟 Key Insights

- Employees with **low job satisfaction** and **high overtime** show higher attrition risk.  
- **Attrition rates** are higher among employees with **under 3 years of tenure**.  
- **Work-life balance** and **environment satisfaction** strongly impact retention and overall performance.

---

## 🧩 Future Enhancements

- 📤 **Publish to Power BI Service** and enable **scheduled data refresh** for real-time analytics.  
- ⚙️ **Integrate Power Automate** to trigger HR alerts for at-risk employees.  
- 🧠 Experiment with **SHAP** or **LIME** for AI explainability in predictive modeling.  

---

## 👨‍💻 Author

**Gopikashree PR**  
_Data Analyst | Power BI Developer | Machine Learning Enthusiast_  

📧 [your.email@example.com](mailto:gopikassakipog@gmail.com)  
🌐 [LinkedIn Profile](https://www.linkedin.com/in/gopikashree-pr)

---

⭐ **If you found this project useful, consider giving it a star on GitHub!**  

---
