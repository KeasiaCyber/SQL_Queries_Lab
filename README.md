<h1>Apply filters to SQL queries</h1>


<h2>Description</h2>
 My organization is working to make their system more secure. It is my job to ensure the system
 is safe, investigate a l potential security issues, and update employee computers as needed.
 The folowing steps provide examples of how I used SQL with lters to perform security-related tasks.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Linux</b> 
- <b>SQL</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Qwiklabs </b>

<h2>Lab walk-through:</h2>

<p align="center">
Retrieve after hours failed login a empts: <br/>
There was apotential security incident that occurred a er business hours (after 1800). All after hours login attempts that failed need to be investigated.The folowing code demonstrates how I created a SQL query to lter for failed login attempts
that occurred after business hours.<br/>
  
<img src="https://imgur.com/XXwRm96.png" height="80%" width="80%" alt="login_in_attempts"/>
  
In the screenshot, the first part shows my query, and the second part displays a portion of the output. This query filters for failed login attempts that occurred after 18:00. Initially, I selected all data from the log_in_attempts table. Then, using a WHERE clause with an AND operator, I filtered the results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition, login_time > '18:00', filters for attempts occurring after 18:00. The second condition, success = FALSE, filters for failed login attempts. <br />
<br />


Retrieve login attempts on specific dates:  <br/>
Asuspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated. The folowing code demonstrates how I created a SQL query to lter for login a empyts that occurred on specific dates. <br/>

<img src="https://imgur.com/CDcn2bU.png" height="80%" width="80%" alt="Dates"/>

In the screenshot, the first part shows my query, and the second part is a portion of the output. This query returns all login attempts that occurred on either 2022-05-09 or 2022-05-08. Initially, I selected all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter the results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08. <br />
<br />


Retrieve login attempts outside of Mexico: <br/>
After investigating the organization’s data on login attempts, I believe there is an issue with the
login attempts that occurred outside of Mexico. These login attempts should be investigated.<br/>

<img src="https://imgur.com/ZOpQMaZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

The query retrieves login attempts from countries other than Mexico. I filtered out Mexico using a NOT clause with LIKE 'MEX%' to match both 'Mexico' and 'MEXICO'. <br />
<br />


Retrieve employees in Marketing:  <br/>
My team wants to update the computers for certain employees in the Marketing department.
To do this, I have to get information on which employee machines to update.
The folowing code demonstrates how I created a SQL query to filter for employee machines
from employees in the Marketing department in the East building.<br/>

<img src="https://imgur.com/GwZoeD8.png" height="80%" width="80%" alt="country"/>

The query retrieves all employees in the Marketing department located in the East building. Initially, I selected all data from the employees table. Then, I used a WHERE clause with AND to filter for employees working in the Marketing department and in the East building. I used LIKE with 'East%' to match the specific office number representing the East building. The first condition filters for employees in the Marketing department (department = 'Marketing'), and the second condition filters for employees in the East building (office LIKE 'East%').<br />
<br />


Retrieve employees in Finance or Sales:  <br/>
The machines for employees in the Finance and Sales departments also need to be updated.
Since a di erent security update is needed, I have to get information on employees only from
these two departments. The folowing code demonstrates how I created a SQL query to lter for employee machines
from employees in the Finance or Sales departments.<br/>

<img src="https://imgur.com/3onVMHO.png" height="80%" width="80%" alt="departmentFS"/>

The query retrieves all employees in the Finance and Sales departments. Initially, I selected all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in either the Finance or Sales departments. I used the OR operator because I want all employees who are in either department. The first condition, department = 'Finance', filters for employees from the Finance department. The second condition, department = 'Sales', filters for employees from the Sales department.<br />
<br />

Retrieve all employees not in IT:  <br/>
My team needs to make one more security update on employees who are not in the
Information Technology department. To make the update, I rst have to get information on
these employees. The folowing demonstrates how I created a SQL query to lter for employee machines from
employees not in the Information Technology department.<br/>

<img src="https://imgur.com/e7NmhBK.png" height="80%" width="80%" alt="it"/>

Theres the part of the screen shot is my query, and the second part is a portion of the output. The
query returns al employees not in the Information Technology department. First, I started by
selecting all data from the employees table. Then, I used a WHERE clause with NOT to lter for
employees not in this department.<br />
<br />

Summary:  <br/>
I filtered data from the 'log_in_attempts' and 'employees' tables using SQL queries. I utilized operators like AND, OR, and NOT, as well as LIKE with the '%' wildcard to extract specific information.<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
