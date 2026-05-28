# Employer-Attrition-Analysis
A data analysis project focused on exploring and modeling employee attrition, identifying key drivers of turnover, visualizing workforce trends, and building predictive models to help organizations proactively reduce employee churn.

📊 Dashboard Overview
The dashboard provides a comprehensive view of employee attrition across multiple dimensions:
MetricValueTotal Employees1,470Attrited Employees176Active Employees1,290Overall Attrition Rate12%Average Salary$10.5KAverage Years at Company10.9

🔍 Key Insights
Department: Research & Development has the highest attrition rate at 13.43%, followed by Sales (12.07%) and Human Resources (10.45%)
Job Role: Human Resources roles lead attrition at 13.01%, while Laboratory Technicians have the lowest at 9.77%
Overtime: Employees working overtime have a significantly higher attrition rate of 17.0% vs. 6.4% for those who don't
Business Travel: Frequent travelers show the highest attrition at 14.84%, compared to 9.03% for non-travelers
Satisfaction: Healthcare Representatives earn the most ($11,389 avg.) but report the lowest job satisfaction (2.40)


🛠️ Tools Used
Microsoft Excel — Data cleaning, preparation, and transformation
Power BI — Interactive dashboard design and data visualization


📐 DAX Measures
Key measures used to power the dashboard calculations:
Total Employees
daxTotal Employees = COUNT(HR_Data[EmployeeNumber])
Attrited Employees
daxAttrited Employees = 
CALCULATE(COUNT(HR_Data[Attrition]), HR_Data[Attrition] = "Yes")
Active Employees
daxActive Employees = 
CALCULATE(COUNT(HR_Data[Attrition]), HR_Data[Attrition] = "No")
Attrition Rate
daxAttrition Rate = 
DIVIDE([Attrited Employees], [Total Employees], 0)
Average Salary
daxAverage Salary = AVERAGE(HR_Data[MonthlyIncome])
Average Years at Company
daxAvg Years at Company = AVERAGE(HR_Data[YearsAtCompany])
Attrition Rate by Department
daxAttrition Rate by Dept = 
DIVIDE(
    CALCULATE(COUNT(HR_Data[Attrition]), HR_Data[Attrition] = "Yes"),
    CALCULATE(COUNT(HR_Data[Attrition])),
    0
)
Average Job Satisfaction
daxAvg Job Satisfaction = AVERAGE(HR_Data[JobSatisfaction])
Average Environment Satisfaction
daxAvg Env Satisfaction = AVERAGE(HR_Data[EnvironmentSatisfaction])
Average Relationship Satisfaction
daxAvg Rel Satisfaction = AVERAGE(HR_Data[RelationshipSatisfaction])

📁 Repository Structure
HR-Attrition-Dashboard/
│
├── data/
│   └── hr_attrition_data.xlsx       # Cleaned dataset
│
├── dashboard/
│   └── HR_Attrition_Dashboard.pbix  # Power BI dashboard file
│
└── README.md

🚀 How to Use
Clone this repository
Open hr_attrition_data.xlsx to explore the raw and cleaned data
Open HR_Attrition_Dashboard.pbix in Power BI Desktop
Use the slicers (Department, Marital Status, Gender) to filter and explore the data interactively


👤 Author
Anzuku Gilbert
📧 anzukugil@gmail.com
