# Pewlett-Hackard-Analysis
## Overview
The purpose of this analysis is to address the aging workforce at Pewlett Hackard. Bobby's manager has given two assignments to determine the number of retiring employees per title, and identify employees who are eligible to participate in a mentorship program. This detailed Analysis report will help  Bobby’s manager for the “silver tsunami” as many current employees reach retirement age.

## Resources
### Data Source: 
  - [departments.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/departments.csv)
  - [employees.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/employees.csv)
  - [dept_manager.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/dept_manager.csv)
  - [dept_emp.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/dept_emp.csv)
  - [salaries.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/salaries.csv)
  - [titles.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/titles.csv)
### Software: 
  - PostgreSQL 11.9
  - pgAdmin 4


## Results:

Pewlett Hackard currently stores their employee data in 6 different csv files. Here is the entity relationship diagram of those datasets:

<img width="697" alt="Screen Shot 2021-11-30 at 10 33 23 AM" src="https://user-images.githubusercontent.com/92277581/144543133-c6815c3e-edd9-4915-be70-0f57aa4fb243.png">


**1. The Number of Retiring Employees by Title**

To determine the number of employees approaching retirement eligibility, We have created a new table [retirement_titles.csv](https://raw.githubusercontent.com/NensiH/Pewlett-Hackard-Analysis/main/Data/retirement_titles.csv) which contains duplicate data in employee name column as many employees have changed their titles during their career. By using DISTINCT ON function, here is the data with most recent job title for each employee(No duplicate data): [unique_titles.csv](https://raw.githubusercontent.com/NensiH/Pewlett-Hackard-Analysis/main/Data/unique_titles.csv)

<img width="475" alt="Screen Shot 2021-12-02 at 10 19 17 PM" src="https://user-images.githubusercontent.com/92277581/144544609-976cdbca-97f9-4a6f-9e50-634082c5cc45.png">

With the data from this table, we were able to retrieve the number of employees by most recent job title that were about to retire. Here is The [retiring_titles.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/retiring_titles.csv) table with counts of employee retiring:


<img width="209" alt="Screen Shot 2021-12-02 at 10 41 51 AM" src="https://user-images.githubusercontent.com/92277581/144464957-57d3229d-1ff3-4b5a-9516-5402dc6a1a7d.png">

 By looking into this data, 
- 90,398 employees or 37.7% of the company's total current employees will be retiring soon.
- 29414 employees are senior engineers
- 28254 employees are senior staff
- 14222 employees are engineers
- 12243 employees are staff
- 4502 employees are Technique Leader
- 1761 employees are Assistant Engineer
- Only 2 Managers will be retiring soon.



**2. The Employees Eligible for the Mentorship**

Next, we were asked to find employees that are eligible to participate in PH's mentorship program. The goal of this program is to train star employees to fill the positions of retiring employees. Here is the data as per the [mentorship_eligibilty.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/mentorship_eligibilty.csv) :

<img width="709" alt="Screen Shot 2021-12-02 at 10 33 26 PM" src="https://user-images.githubusercontent.com/92277581/144545778-c810c099-52f3-493c-baac-dcae5b76336a.png">


Using COUNT function, Here is the table with the total numbers of employees from all departments eligible for this program based on the current criteria: 

<img width="207" alt="Screen Shot 2021-12-02 at 10 40 22 AM" src="https://user-images.githubusercontent.com/92277581/144464714-1bb15506-6d21-45b6-a0ae-8d1ef32d61fb.png">

- There are 1,549 employees eligible for PH's mentorship program.
- 424 employees are senior staff
- 394 employees are engineers
- 300 employees are staff
- 293 employees are Senior Engineer
- 77 employees are Technique Leader
- 61 employees are Assistant Engineer
- There are no managers eligible for this program based on the current criteria



## Summary:

1. How many roles will need to be filled as the "silver tsunami" begins to make an impact?
  
     Looking at both of these analyses, we can see that of the 90,396 potential spaces that need to be filled due to retirement.

2. Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?
     There are only 1,550 employees currently eligible to mentor new employees to fill those positions. That means there is one mentor for every 58 new employees, so we can conclude that there is not enough mentors to prepare the next generation of Pewlett Hackard employees.
