# Pewlett-Hackard-Analysis
## Overview
The purpose of this analysis is to address the aging workforce at Pewlett Hackard. Bobby's manager has given two assignments to determine the number of retiring employees per title, and identify employees who are eligible to participate in a mentorship program. This detailed Analysis report will help  Bobby’s manager for the “silver tsunami” as many current employees reach retirement age.

## Resources
- Data Source: 
  - [departments.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/departments.csv)
  - [employees.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/employees.csv)
  - [dept_manager.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/dept_manager.csv)
  - [dept_emp.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/dept_emp.csv)
  - [salaries.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/salaries.csv)
  - [titles.csv](https://github.com/NensiH/Pewlett-Hackard-Analysis/blob/main/Data/titles.csv)
- Software: 
  - PostgreSQL 11.9
  - pgAdmin 4


## Results:

Pewlett Hackard currently stores their employee data in 6 different csv files. Here is the entity relationship diagram of those datasets.

<img width="697" alt="Screen Shot 2021-11-30 at 10 33 23 AM" src="https://user-images.githubusercontent.com/92277581/144543133-c6815c3e-edd9-4915-be70-0f57aa4fb243.png">


**1. The Number of Retiring Employees by Title**

To determine the number of employees approaching retirement eligibility, Here we have created a new table and which contains duplicate data in employee name column as many employees have changed their titles during their career. By using DISTINCT ON function, here is the data with most recent job title for each employee(No duplicate data):

<img width="475" alt="Screen Shot 2021-12-02 at 10 19 17 PM" src="https://user-images.githubusercontent.com/92277581/144544609-976cdbca-97f9-4a6f-9e50-634082c5cc45.png">

With the data from this table, we were able to retrieve the number of employees by most recent job title that were about to retire. Here is The retiring_titles table with counts of employee retiring:


<img width="209" alt="Screen Shot 2021-12-02 at 10 41 51 AM" src="https://user-images.githubusercontent.com/92277581/144464957-57d3229d-1ff3-4b5a-9516-5402dc6a1a7d.png">


- By looking into this data, 90,398 employees or 37.7% of the company's total current employees will be retiring soon.
- Senior Engineer, Senior Staff and Engineer will be the most impacted positions with respectively 29,414, 28,254 and 14,222 futures retirees.
- Only 2 Managers will be retiring soon.



**2. The Employees Eligible for the Mentorship **
Next, we were asked to find employees that are eligible to participate in PH's mentorship program. The goal of this program is to train star employees to fill the positions of retiring employees. Here is the data as per the mentorship_eligibility table:

<img width="709" alt="Screen Shot 2021-12-02 at 10 33 26 PM" src="https://user-images.githubusercontent.com/92277581/144545778-c810c099-52f3-493c-baac-dcae5b76336a.png">


Using COUNT function, Here is the table with the employees from all departments: 

Program<img width="207" alt="Screen Shot 2021-12-02 at 10 40 22 AM" src="https://user-images.githubusercontent.com/92277581/144464714-1bb15506-6d21-45b6-a0ae-8d1ef32d61fb.png">

- There are 1,549 employees eligible for PH's mentorship program.
- 424 employees are senior staff
- 394 employees are engineers
- 300 employees are staff
- 293 employees are Senior Engineer
- 77 employees are Technique Leader
- 61 employees are Assistant Engineer
- There are no managers eligible for this program based on the current criteria
