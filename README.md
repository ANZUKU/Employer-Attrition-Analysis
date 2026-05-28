# HR Attrition Dashboard

## Overview

The HR Attrition Dashboard is an interactive tool developed in **Power BI** and **Microsoft Excel** to analyze and visualize workforce data. It empowers HR professionals and management teams to uncover attrition patterns, monitor turnover trends, and design actionable strategies to improve employee retention.

This dashboard delivers insights into key metrics such as attrition rates, department-wise turnover, job role-specific trends, overtime impact, business travel frequency, and satisfaction scores — facilitating informed, data-driven decision-making.

---

## Dataset Overview

The dataset consists of **1,470 employee records** with attributes across the following categories:

- **Attrition**: Departure indicators (Yes/No)
- **Demographics**: Age, gender, marital status, and education level
- **Work Metrics**: Monthly income, years at the company, overtime, and travel frequency
- **Feedback Metrics**: Job satisfaction, environment satisfaction, relationship satisfaction, and work-life balance

---

## Tools Used

- **Power BI**: For creating dynamic and interactive dashboards
- **Microsoft Excel**: For data cleaning, transformation, and preparation

---

## Key Metrics

| Metric                   | Value   |
|--------------------------|---------|
| Total Employees          | 1,470   |
| Attrited Employees       | 176     |
| Active Employees         | 1,290   |
| Overall Attrition Rate   | 12%     |
| Average Salary           | $10.5K  |
| Average Years at Company | 10.9    |

---

## Features

### 1. **Key Metrics and Visualizations**
- **Attrition Rate**: Overall percentage of employees leaving the organization
- **Attrition by Department**: Identification of departments with the highest turnover
- **Attrition by Job Role**: Highlighting roles most impacted by attrition
- **Attrition by Overtime**: Comparison of attrition between employees who work overtime vs. those who don't
- **Attrition by Business Travel**: Turnover rates segmented by travel frequency

### 2. **Trends Analysis**
- **Overtime Impact**: Employees on overtime are nearly 3× more likely to leave (17.0% vs. 6.4%), suggesting burnout as a critical driver
- **Business Travel**: Frequent travelers have the highest attrition at 14.84%, compared to 9.03% for non-travelers
- **Department Trends**: Research & Development leads departmental attrition at 13.43%, followed by Sales at 12.07%
- **Satisfaction Scores**: Low satisfaction scores are observed across all roles (avg. 2.55/4), indicating a widespread engagement challenge

### 3. **Actionable Strategies**
Based on insights from the data:
- **Overtime**: Introduce compensatory time off or overtime limits to reduce burnout-driven exits
- **Business Travel**: Offer remote work alternatives or travel allowances to frequent travelers
- **R&D & Sales Roles**: Implement structured career paths, mentorship, and targeted retention programs
- **New Employees**: Enhance onboarding processes, mentorship opportunities, and feedback systems

---

## Dashboard Overview

### **HR Attrition Dashboard**
The main dashboard provides a high-level summary of attrition metrics and acts as a navigation hub for exploring deeper insights. It includes KPI cards, attrition by department, job role, overtime, and business travel, as well as a satisfaction breakdown table by job role.

![HR Attrition Dashboard](Attrition_dashbaord.pdf)

---

## DAX Measures

Key measures used to power the dashboard calculations:

**Total Employees**
```dax
Total Employees = COUNT(HR_Data[EmployeeNumber])
```

**Attrited Employees**
```dax
Attrited Employees =
CALCULATE(COUNT(HR_Data[Attrition]), HR_Data[Attrition] = "Yes")
```

**Active Employees**
```dax
Active Employees =
CALCULATE(COUNT(HR_Data[Attrition]), HR_Data[Attrition] = "No")
```

**Attrition Rate**
```dax
Attrition Rate =
DIVIDE([Attrited Employees], [Total Employees], 0)
```

**Average Salary**
```dax
Average Salary = AVERAGE(HR_Data[MonthlyIncome])
```

**Average Years at Company**
```dax
Avg Years at Company = AVERAGE(HR_Data[YearsAtCompany])
```

**Attrition Rate by Department**
```dax
Attrition Rate by Dept =
DIVIDE(
    CALCULATE(COUNT(HR_Data[Attrition]), HR_Data[Attrition] = "Yes"),
    CALCULATE(COUNT(HR_Data[Attrition])),
    0
)
```

**Average Job Satisfaction**
```dax
Avg Job Satisfaction = AVERAGE(HR_Data[JobSatisfaction])
```

**Average Environment Satisfaction**
```dax
Avg Env Satisfaction = AVERAGE(HR_Data[EnvironmentSatisfaction])
```

**Average Relationship Satisfaction**
```dax
Avg Rel Satisfaction = AVERAGE(HR_Data[RelationshipSatisfaction])
```


## Usage Instructions

1. Open the Power BI dashboard file [Employee Attrition.pbix](Employee Attrition.pbix)
2. Explore the visualizations and metrics:
   - Navigate through department, job role, and satisfaction-specific insights
   - Filter by attributes such as **Department**, **Marital Status**, and **Gender** to view tailored data
3. Use the insights to inform HR strategies and initiatives for workforce retention

---

---

## Conclusion

**"Retention isn't just about reducing attrition; it's about creating a workplace where employees want to stay and grow."**

With this dashboard, organizations can transition from reactive to proactive HR management — leveraging data to craft informed retention strategies that address the root causes of employee turnover.

---

## Author

**Anzuku Gilbert**

- **Email:** [anzukugil@gmail.com](mailto:anzukugil@gmail.com)

---
