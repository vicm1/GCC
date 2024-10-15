Task 1. Match employees to their machines
First, you must identify which employees are using which machines. The data is located in the machines and employees tables.

You must use a SQL inner join to return the records you need based on a connecting column. In the scenario, both tables include the device_id column, which you’ll use to perform the join.

1. Run the following query to retrieve all records from the machines table:
SELECT *
FROM machines;

2. Write a query to perform an inner join between the machines and employees tables on the device_id column.
- SELECT *
FROM machines
INNER JOIN employees ON employees.device_id = machines.device_id;

How many rows did the inner join return?
- 185

Task 2. Return more data
You now must return the information on all machines and the employees who have machines. Next, you must do the reverse and retrieve the information of all employees and any machines that are assigned to them.

To achieve this, you’ll complete a left join and a right join on the employees and machines tables. The results will include all records from one or the other table. You must link these tables using the common device_id column.

1. Write a SQL query to connect the machines and employees tables through a left join.
- SELECT *
FROM machines
LEFT JOIN employees ON machines.device_id = employees.device_id;

What is the value in the username column for the last record returned?
- NULL

2. Write a SQL query to connect the machines and employees tables through a right join.
- SELECT *
FROM machines
RIGHT JOIN employees ON machines.device_id = employees.device_id;


Task 3. Retrieve login attempt data
To continue investigating the security incident, you must retrieve the information on all employees who have made login attempts. To achieve this, you’ll perform an inner join on the employees and log_in_attempts tables, linking them on the common username column.

1. Write a SQL query to perform an inner join on the employees and log_in_attempts tables.
- SELECT *
FROM employees
INNER JOIN log_in_attempts ON employees.username = log_in_attempts.username;

How many records are returned by this inner join?
- 200
