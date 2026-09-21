# 👥 HR Employee Attrition Analysis

**Exploratory analysis of who leaves a company and which factors go with it**: department, overtime, pay, tenure, job satisfaction and work-life balance.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)

**Jump to:** [Approach](#-approach) · [Key findings](#-key-findings) · [Caveats](#-caveats) · [Run it](#-run-it)

---

## 🧭 Approach

1. Keep the columns relevant to attrition: age, department, job role, gender, monthly income, years at company, overtime, job satisfaction, work-life balance.
2. Convert the `Attrition` label (Yes/No) to 1/0 so group averages equal attrition rates.
3. Compare attrition across groups with `groupby`, and visualize with bar charts.

---

## 🔎 Key findings

Overall, **16.1%** of employees in the dataset left.

**Attrition rate by overtime:** 10.4% without overtime vs **30.5%** with overtime.

**Group averages, employees who stayed vs left**

| Factor | Stayed | Left |
|---|---|---|
| Average monthly income | 6,833 | **4,787** |
| Average years at company | 7.4 | **5.1** |
| Average job satisfaction (1-4) | 2.78 | 2.47 |
| Average work-life balance (1-4) | 2.78 | 2.66 |

**Attrition by department**

| Department | Attrition rate |
|---|---|
| Sales | 20.6% |
| Human Resources | 19.0% |
| Research & Development | 13.8% |

### What stands out

- **Overtime is the strongest signal:** employees working overtime left about **3x** as often (30.5% vs 10.4%).
- Leavers earned noticeably less and had a shorter tenure, pointing to early-career, lower-paid employees as the highest-risk group.
- Sales and HR lose more people than R&D.

### Suggested actions (business view)

- Review overtime workload, especially in Sales.
- Focus retention effort on employees with under ~5 years of tenure and lower pay bands.
- Track satisfaction and work-life-balance scores as early-warning indicators.

---

## ⚠️ Caveats

- These are **descriptive, one-factor comparisons**. They show association, not cause, and factors overlap (for example, lower income and shorter tenure go together).
- No statistical tests or predictive model are included.
- The dataset is imbalanced (about 16% attrition), so any future model should be judged on recall/F1, not accuracy.

**Possible extensions:** a logistic regression or tree model with feature importance, and a combined view (overtime × department × tenure).

---

## 🚀 Run it

```bash
git clone https://github.com/Sajal-10903/HR_Attrition_Analysis.git
cd HR_Attrition_Analysis
pip install -r requirements.txt
jupyter notebook HR_Attrition_Analysis.ipynb
```

The dataset is not included in the repository. The notebook reads it from `data/hr_data.csv`, so create a `data/` folder and place the HR dataset there (columns include Age, Attrition, Department, JobRole, Gender, MonthlyIncome, YearsAtCompany, OverTime, JobSatisfaction, WorkLifeBalance).

---

**Author:** [Sajal Raj](https://github.com/Sajal-10903) · [Portfolio](https://sajalraj-portfolio.vercel.app) · [LinkedIn](https://www.linkedin.com/in/sajal-raj-456b31252/)
