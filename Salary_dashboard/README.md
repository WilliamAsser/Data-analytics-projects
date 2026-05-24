# Excel-Portfolio

Excel data analytics projects built during self-study, including 
interactive dashboards, array formulas, Power Query and data visualizations.

## Projects

### 1. Salary Dashboard
<img width="2098" height="870" alt="image" src="https://github.com/user-attachments/assets/0317c7f9-fb76-473a-b3b4-c8ded8bb2c3e" />

An interactive Excel dashboard analyzing salary data across job titles, 
countries and job types.

# Skills used:
* Charts
* Formulas and Functions
* Data Validation

# Data Jobs Dataset
The dataset used for this project contains real-world data science job information from 2023. Please find attached the dataset 
The dataset includes detailed information on:
* Job titles
* Salaries
* Locations
* Skills

## Dashboard Build

* Charts
* Data Science Job Salaries - Bar Chart
<img width="596" height="404" alt="image" src="https://github.com/user-attachments/assets/716de63b-8518-46be-951a-5b4c15bba3ce" />

* Excel Features: Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
* Design Choice: Horizontal bar chart for visual comparison of median salaries.
* Data Organization: Sorted job titles by descending salary for improved readability.
* Insights Gained: This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

Country Median Salaries - Map Chart
<img width="555" height="339" alt="image" src="https://github.com/user-attachments/assets/9b4ae901-eee3-44a1-af15-31c2cb9f53c9" />
* Excel Features: Utilized Excel's map chart feature to plot median salaries globally.
* Design Choice: Color-coded map to visually differentiate salary levels across regions.
* Data Representation: Plotted median salary for each country with available data.
* Visual Enhancement: Improved readability and immediate understanding of geographic salary trends.
* Insights Gained: Enables quick grasp of global salary disparities and highlights high/low salary regions.

## Formulas and Functions

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```
* Multi-Criteria Filtering: Checks job title, country, schedule type, and excludes blank salaries.
* Array Formula: Utilizes MEDIAN() function with nested IF() statement to analyze an array.
* Tailored Insights: Provides specific salary information for job titles, regions, and schedule types.
* Formula Purpose: This formula populates the table below, returning the median salary based on job title, country, and type specified.

Background Table
<img width="263" height="218" alt="image" src="https://github.com/user-attachments/assets/c144aac9-c965-4b98-9076-7bca18442f82" />


Dashboard Implementation
<img width="659" height="723" alt="image" src="https://github.com/user-attachments/assets/ebbe7c29-61fa-481c-9603-18f8e42d63b1" />


Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```
* Unique List Generation: This Excel formula below employs the FILTER() function to exclude entries containing "and" or commas, and omit zero values.
* Formula Purpose: This formula populates the table below, which gives us a list of unique job schedule types.

Background Table
<img width="190" height="117" alt="image" src="https://github.com/user-attachments/assets/cccc06de-b62c-4334-8886-e3f886067984" />

Dashboard Implementation:
<img width="669" height="724" alt="image" src="https://github.com/user-attachments/assets/d46dcff4-01ec-4d5b-a979-a501df84d516" />

Data Validation
* Filtered List
* Enhanced Data Validation: Implementing the filtered list as a data validation rule under the Job Title, Country, and Type option in the Data tab ensures:
* User input is restricted to predefined, validated schedule types
* Incorrect or inconsistent entries are prevented
* Overall usability of the dashboard is enhanced

### Conclusion
________________________________________________________________________________
I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from my Excel course, this dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries.



