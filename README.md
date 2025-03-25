# DataCampHRAnalytics
Power BI based HR Analytics dashboard prepared as part of case study based course work at Data Camp

The dashboard was created in Power BI as a part of the course "Case Study in HR Analytics" in Data Camp.
Here are screenshots from the dashboard, followed by notes on data preparation, data modelling, data visualization and report building.

![image](https://github.com/user-attachments/assets/6d0a6436-c878-49ee-b1bd-4e3358cc7872)

![image](https://github.com/user-attachments/assets/967578b3-cc7d-43aa-ab37-14b274218e02)

![image](https://github.com/user-attachments/assets/858517a7-6959-43a7-b2cd-286698af5663)

![image](https://github.com/user-attachments/assets/538bdb6e-8a34-47fd-bde8-7dd1f9668bcf)

![image](https://github.com/user-attachments/assets/b13ccd59-7a6b-4c50-aaa9-49cfe529d5c9)


Background

I applied concepts relating to data preparation, data modelling, creating and using DAX measures, creating appropropriate visualizations and finally providing a consistent and cohesive reporting for the end user.
The intended user for this dashboard would be someone who works in the HR department as a HR professional or a HR analyst tasked with providing information and/or insights to their colleagues in the HR function.

Data Preparation

There were a few datasets in .csv format which were imported into Power BI and some data cleansing/transformation tasks were done using Power Query Editor.
There are four dimension tables (education level, rating level, satisfaction level and employee meta data). 
One fact table consisted of data across employee IDs and time relating to performance reviews.
A dimension date table was created using the CALENDAR function as well.
A custom column to store age categories based on employee age.


Data Modelling

![image](https://github.com/user-attachments/assets/02aa2789-809c-41ae-92bd-6aee8cfa1d31)

I inspected and confirmed the relationships that were automatically created by Power BI once the datasets were imported. It was essential to ensure the relationships were appropriately set between the various dimension tables and the fact table.

Please note that there are two relationships (to represent self rating and manager rating)  between the rating level table and employee fact table, and four relationships between the satisfaction level table (to represent environment satisfaction, work life balance satisfaction, relationship satisfaction and job satisfaction).

Power BI will only keep one such relationship between two tables active at a time. The other relationships can be used when required using the USERELATIONSHIP() function when creating measures.

A separate table called _Measures was created to store all the measures within this table. This was a best practice suggested by the Data Camp instructor as it enables all measures to be housed in a separate table for easy understanding/referencing.

A number of measures were created to be used in data visulizations. The screenshot here shows all the measures created.

![image](https://github.com/user-attachments/assets/b0938543-c5fa-4c63-bb77-a082d168f5fb)

The DAX measures essentially used functions such as DIVIDE, CALCULATE with COUNT (for example, to count number of active employees), AVERAGE, MAX, IF

An example of measure using the USERELATIONSHIP() function

![image](https://github.com/user-attachments/assets/36330390-b7e6-48a0-8e12-896b40359e7c)


Data Visualization
Here is a quick summary of the different visuals created. I created different tabs to group visulizations of specific topic together.

![image](https://github.com/user-attachments/assets/25039550-94f1-4b1c-9c8c-9cf16f0a47ce)

[1] Overview - Provides KPIs in the form of employee counts and attrition rate , trends in number of employees, employee size by department 
[2] Demographics - Distribution of active employees by age categories, by age & gender, by marital status and by ethinicity. This information could be useful to the organization in understanding the extent of diversity in their workforce.
[3] Salary - The objective is to analyze the salary trends by age category, gender, education level and ethnicity. 
[4] Performance -In this tab, the objective is to query the performance details for a selected employee and see their trends in performance and satisfaction ratings. For an employee who has already had reviews in the past, the latest review date will be shown, otherwise "No Review Yet" will be displayed. The next review date for an employee will be either 1 year from their last review date or 1 year from the hire date whichever is later. A DAX measure was created to help reflect this logic.

![image](https://github.com/user-attachments/assets/a9a06cd6-3738-4b55-a922-bdc4761738cb)


![image](https://github.com/user-attachments/assets/5017c394-e9ca-4f61-9e2b-32561fd3cf99)





Report Design

The dashboard was formatting to provide consistent formatting across the visuals. A custom theme was created to use standardized fonts, font sizes and color themes.
A navigator was added to help easier navigation across the different tabs.



