Task 1. List all organization machines
In this task, you need to get a list of all organization machines and their operating systems. The data is contained in the machines table. You’ll need to use the SELECT keyword to return specific columns.

1. Run a SQL query to retrieve only the device_id and operating_system columns from the machines table.
- SELECT device_id, operating_system
FROM machines;
How many rows were returned from the machines table? (You can view the number of rows at the bottom of the output.)
- 200

Task 2. Retrieve a list of the machines with OS 2
In this task, you need to obtain a list of all machines with the 'OS 2' operating system because these machines need an update. To get this information, you’ll run your first SQL query with a filter.

1. Select all the records from the machines table with a value of 'OS 2' in the operating_system column. Replace the value X with the correct string:
- SELECT *
FROM machines WHERE operating_system = 'OS 2';

How many machines in the database use the OS 2 operating system?
- 80


Task 3. List employees in specific departments
In this task, you need to retrieve a list of all the employees in the Finance and Sales departments to obtain their office numbers. A notice about handling confidential financial information will be posted to these offices.

1. Filter the rows returned from department column in the employees table to include only employees from the 'Finance' department. Replace X with the appropriate column name and Y with the appropriate value to complete the filter:
- SELECT *
FROM employees WHERE department = 'Finance';

What is the employee_id of the first row returned?
- 1003

2. Modify the previous query so that it returns employees who are in the 'Sales' department.
How many employees work in the Sales department?
- 33

Task 4. Identify employee machines
Your team recently discovered that there are issues with machines in the South building. In this task, you need to obtain certain employee and computer information.

A machine in 'South-109' has an issue. You need to determine which employee uses that computer so you can send them an alert.

1. Write a query to identify which employee uses the office in 'South-109'. (The data must be returned from the office column in the employees table.)
- SELECT * FROM employees WHERE office = 'South-109';

Which of the following employees uses the computer with the issue?
- jlansky

Next, your team has determined that there is an issue with all the machines in the South building. Offices in the organization are named with the building name, a hyphen, and the office number in that building (for example, 'South-109').

2. Modify the query you used in the previous step so that it returns information on all the employees in the 'South' building. Use the LIKE operator with % in this query.
- SELECT * FROM employees WHERE office LIKE'South%';

Which department does the first employee listed in the South building belong to?
- Finance
