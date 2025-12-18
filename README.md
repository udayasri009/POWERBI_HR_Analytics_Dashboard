# HR-Analytics-Dashboard (Interactive Dashboard Creation Using Excel)
## Project Objective
To analyze HR data using Power BI to understand employee attrition, workforce demographics, and departmental trends, and to provide actionable insights that help HR teams improve employee retention, optimize workforce planning, and support data-driven decision-making.

## Dataset used
- <a href ="https://github.com/udayasri009/POWERBI_HR_Analytics_Dashboard/blob/main/HR%20Data.xlsx">Dataset</a>

## Questions (KPIS)

-What is the total number of employees in the organization?

-How many employees have left the company (attrition count)?

-What is the overall attrition rate?

-What is the average age of employees?

-What is the average salary of employees?

-What is the average tenure of employees in the company?

## Dashboard Insight Questions

-Which age group has the highest attrition rate?

-Which education background shows maximum employee attrition?

-Which salary slab has the highest attrition?

-How does attrition vary based on years at the company?

-Which job roles contribute most to attrition?

-Which department has the highest employee attrition?

-Does business travel frequency impact employee attrition?

-What is the gender-wise distribution of attrition?

-How does marital status affect employee attrition?

# Filter-Wise (Slicer) Questions

## Age Group Filter
-How does attrition change for different age groups?

-Which age group is most likely to leave the company?

## Department Filter

-What is the attrition trend within a specific department?

-Which department has the highest or lowest attrition rate?

## Education Field Filter

-How does attrition vary by education background?

-Which education field has higher employee turnover?

## Business Travel Filter

-Do employees who travel frequently have higher attrition?

-How does non-travel vs travel impact attrition?

- Dashboard Interactions <a href = "https://github.com/udayasri009/POWERBI_HR_Analytics_Dashboard/blob/main/HR%20ANALYSIS%20PROJECT%20POWERBI.pbix">View Dashboard</a>

# FORMULAS

Total Employees = COUNT(HR_Data[EmployeeID])

Attrition Count =CALCULATE(
                          COUNT(HR_Data[EmployeeID]),
                          HR_Data[Attrition] = "Yes"
)

Active Employees =
CALCULATE(
    COUNT(HR_Data[EmployeeID]),
    HR_Data[Attrition] = "No"
)

Attrition Rate (%)
Attrition Rate =
DIVIDE(
    [Attrition Count],
    [Total Employees],
    0
)

Average Age = AVERAGE(HR_Data[Age])

Average Salary = AVERAGE(HR_Data[MonthlyIncome])

Average Tenure = AVERAGE(HR_Data[YearsAtCompany])

Attrition by Gender =
CALCULATE(
    COUNT(HR_Data[EmployeeID]),
    HR_Data[Attrition] = "Yes"
)

Attrition by Category =
CALCULATE(
    COUNT(HR_Data[EmployeeID]),
    HR_Data[Attrition] = "Yes"
)

Age Group =
SWITCH(
    TRUE(),
    HR_Data[Age] <= 25, "18-25",
    HR_Data[Age] <= 35, "26-35",
    HR_Data[Age] <= 45, "36-45",
    HR_Data[Age] <= 55, "46-55",
    "55+"
)

Attrition by AgeGroup =
CALCULATE(
    COUNT(HR_Data[EmployeeID]),
    HR_Data[Attrition] = "Yes"
)

Salary Slab =
SWITCH(
    TRUE(),
    HR_Data[MonthlyIncome] <= 5000, "Up to 5k",
    HR_Data[MonthlyIncome] <= 10000, "5k-10k",
    HR_Data[MonthlyIncome] <= 15000, "10k-15k",
    "15k+"
)

Attrition by Salary =
CALCULATE(
    COUNT(HR_Data[EmployeeID]),
    HR_Data[Attrition] = "Yes"
)

Attrition by Years =
CALCULATE(
    COUNT(HR_Data[EmployeeID]),
    HR_Data[Attrition] = "Yes"
)

Attrition by Business Travel =
CALCULATE(
    COUNT(HR_Data[EmployeeID]),
    HR_Data[Attrition] = "Yes"
)

Attrition by Marital Status =
CALCULATE(
    COUNT(HR_Data[EmployeeID]),
    HR_Data[Attrition] = "Yes"
)

## DASHBOARD 
![HR Analytics Dashboard](POWERBI_DASHBOARD.IMG.png)
