# HR-Analytics-Dashboard-using-PowerBI
The Human Resource Report provides a comprehensive view of employee data across various  departments and business units. Its primary purpose is to support HR decision-making by offering  insights into workforce demographics, job classifications, job satisfaction, performance ratings, and other key metrics. This report is designed to monitor and evaluate  employee engagement, performance trends, and potential areas for improvement within the organization. The primary audience for this report includes HR managers, department heads, and executive leadership. This report aims to provide them with actionable insights for workforce planning, retention strategies, and improving overall employee satisfaction. 

## The Objective of the HR Dashboard
Before diving into data, it’s crucial to align with your organization’s HR goals. Identify the specific questions your dashboard aims to answer. What insights are HR professionals seeking to understand employee attrition?

- Composition of the Workforce: Understand the composition of the workforce by department, education field, business travel frequency, gender, job role, and age group.
- HR KPIs: Analyze employee count, average salary, average monthly salary, average age, average salary hike, average Job satisfaction score, and gender ratio.
- Identify trends and patterns in employee data across different parameters like Education, Age group, and Department.
- Analyze different HR KPIs for different Job roles.
- Show the impact of Age & Department on Salary.
- Employee Attrition Analysis: Identify the factors that influence employee turnover and retention, such as salary, age, gender, education, and employee demographics (e.g., age, marital status, work-life balance).
- Gain insights into areas with high attrition rates to inform targeted retention strategies.
- Analyze the attrition rate by various parameters including business travel, job satisfaction, marital status, work-life balance, monthly income, and age.
- Compare the attrition rates in different departments such as Sales, R&D, and HR.
## Data Source
The file contains data related to HR analytics, with 1,480 rows and 38 columns. The dataset contains the following columns: EmpID, Age, AgeGroup, Attrition, BusinessTravel, DailyRate, Department, DistanceFromHome, Education, EducationField, EmployeeCount, EmployeeNumber, EnvironmentSatisfaction, Gender, HourlyRate, JobInvolvement, JobLevel, JobRole, JobSatisfaction, MaritalStatus, MonthlyIncome, SalarySlab, MonthlyRate, NumCompaniesWorked, Over18, OverTime, PercentSalaryHike, PerformanceRating, RelationshipSatisfaction, StandardHours, StockOptionLevel, TotalWorkingYears, TrainingTimesLastYear, WorkLifeBalance, YearsAtCompany, YearsInCurrentRole, YearsSinceLastPromotion, and YearsWithCurrManager.

## DAX Measures
To define the KPIs and DAX measures in Power BI, we need to use the Modeling tab and the DAX language. The Modeling tab is where we can create and manage the KPIs and DAX measures in our data model. The DAX language is the formula language that we use to define the logic and calculation of the KPIs and DAX measures. 
- Attrition Count = CALCULATE([Employee Count], HR_Analytics[Attrition]="Yes")
- DIVIDE ([Attrition Count],CALCULATE ( [Employee Count], ALL ( HR_Analytics[Attrition] ) ),0)
- Attrition Target = 0.2
- Average Age = AVERAGE(HR_Analytics[Age])
- Average Job Satisfaction = AVERAGE(HR_Analytics[JobSatisfaction])
- Average Salary = [Monthly Salary]/[Employee Count]
- Average Salary Hike = AVERAGE(HR_Analytics[PercentSalaryHike])
- Average Years = AVERAGE(HR_Analytics[YearsAtCompany])
- Employee Count = DISTINCTCOUNT(HR_Analytics[EmpID])
- Gender Ratio =
DIVIDE (
    CALCULATE ( [Employee Count], HR_Analytics[Gender] = "Female" ),
    CALCULATE ( [Employee Count], HR_Analytics[Gender] = "Male" ),
    0
)
- Monthly Salary = SUM(HR_Analytics[MonthlyIncome])
## Data Visualizations
![dashboard overview](Screenshot 2024-12-02 170145.png)
![dashboard overview](Screenshot 2024-12-02 170156.png)
## interactivity and functionality to the dashboard in Power BI
To add interactivity and functionality to the dashboard in Power BI, we need to use the Visualizations pane and the Fields pane. The Visualizations pane is where we can choose and modify the visualizations for our data, such as the type, the format, the style, the interactivity, and the functionality. The Fields pane is where we can drag and drop the fields from our data model to the visualizations, and define the roles and values of the fields, such as the axis, the legend, the value, the filter, etc. 

Here are some of the tools and techniques that we can use to add interactivity and functionality to the dashboard:
- Slicer: A slicer is a visualization that allows the users to filter the data by selecting one or more values from a list. We can use a slicer to filter the data by department, education field, business travel, gender, job role, or age group. To add a slicer to the dashboard, we need to select the Slicer icon from the Visualizations pane, and drag and drop the field that we want to filter by from the Fields pane to the Field well in the Visualizations pane. We can also change the format and style of the slicer, such as the orientation, the selection controls, the font, the color, etc.
- Button: A button is a visualization that allows the users to perform an action by clicking on it, such as navigating to another page, opening a bookmark, or resetting the filters. We can use a button to create a menu or a navigation bar for the dashboard. To add a button to the dashboard, we need to select the Button icon from the Visualizations pane, and drag and resize the button on the dashboard. We can also change the format and style of the button, such as the type, the text, the icon, the font, the color, etc. We also need to assign an action to the button, such as the destination page, the bookmark, or the reset option.
- Bookmark: A bookmark is a feature that allows us to save the current state of the dashboard, such as the filters, the selections, the visuals, etc. We can use a bookmark to create different scenarios or views of the dashboard, and link them to the buttons. To create a bookmark, we need to go to the View tab in the ribbon, and select the Bookmarks pane. We can then click on the Add icon to create a new bookmark, and give it a name. We can also update or delete the bookmarks as needed.
- Selection: A selection is a feature that allows us to highlight or filter the data by clicking on a visual element, such as a bar, a slice, or a point. We can use a selection to drill down or cross-filter the data, and see the details or the relationships of the data. To enable or disable the selection, we need to go to the Format tab in the Visualizations pane, and select the Edit interactions icon. We can then choose the type of interaction that we want for each visual element, such as Highlight, Filter, or None.
- Bookmark Navigation: Bookmark navigation is a feature that allows you to create bookmarks for different states of your dashboard, such as the filters, the selections, the visuals, etc. You can then link the bookmarks to buttons or other visuals, and use them to navigate between the different states of your dashboard
- Page navigation: Page navigation is a feature that allows you to create multiple pages for your dashboard, and link them to buttons or other visuals, and use them to navigate between the different pages of your dashboard.
- We have used Slicers in the report to Slice or Filter Reports based on various parameters. And used Button, Bookmark, and Selection to toggle two visuals (Monthly Salary by Department and Employee Count by Department) with one another.
## Drawing Insights from the Dashboard
- The employee attrition rate is 16%, which is higher than the industry average of 12%. The main reasons for attrition are low salaries, high workload, and lack of career growth opportunities.
- The employee diversity and inclusion analysis reveals that there is a significant gap in gender representation, especially in HR, where only 33% are female. The education field is also dominated by Life Sciences & Medical, which accounts for more than 50% of the employees.
- The total employee count is 1233 with an average salary of $6,879 and a monthly total payroll of $8.5M.
- The majority of employees are in the age group of 26-35 (490) and 36-45 (425).
- Sales Executives are the largest job role (269), followed by Research Scientists (245).
- The highest average salaries are drawn by Managers ($17,201) and Research Directors ($15,947).
- Gender ratio is skewed towards one gender at 68%.
- The total attrition count is 237 with an overall attrition rate of 16%.
- Attrition rates vary across departments, with Sales (21%), R&D (19%), and HR (14%) having the highest rates.
- Among job roles, Sales Representatives (40%), Laboratory Technicians (24%), and Human Resources Specialists (23%) have the highest attrition rates.
- Employees who travel frequently for business have a higher attrition rate (25%) compared to those who rarely travel (8%).
- Employees who are dissatisfied with their jobs have a higher attrition rate (23%) compared to those who are satisfied (11%).
- The average age of employees facing attrition is 34.
- Attrition rates vary significantly based on job satisfaction levels; employees with lower job satisfaction have higher attrition rates.
- Single employees face a higher rate of attrition compared to married or divorced employees.

OBSERVATION: Introduce predictive analytics to forecast attrition trends.
Add real-time updates for decision-making.
Integrate employee feedback for deeper insights into job satisfaction.
