Task 1. Retrieve employee device data
In this task, you need to obtain information on employee devices because your team needs to update them. The information you need is in the machines table in the organization database.

First, you need to retrieve all the information about the employee devices.

1. Run the following query to select all device information from the machines table:
- SELECT *
FROM machines;
 - ouput:
 +--------------+------------------+----------------+---------------+-------------+
| device_id    | operating_system | email_client   | OS_patch_date | employee_id |
+--------------+------------------+----------------+---------------+-------------+
| a184b775c707 | OS 1             | Email Client 1 | 2021-09-01    |        1156 |
| a192b174c940 | OS 2             | Email Client 1 | 2021-06-01    |        1052 |
| a305b818c708 | OS 3             | Email Client 2 | 2021-06-01    |        1182 |
| a317b635c465 | OS 1             | Email Client 2 | 2021-03-01    |        1130 |
| a320b137c219 | OS 2             | Email Client 2 | 2021-03-01    |        1000 |
|...           |                  |                |               |             |
+--------------+------------------+----------------+---------------+-------------+
200 rows in set (0.356 sec)

2. Run the following query to select only the device_id and email_client columns from the machines table. Replace X with device_id and Y with email_client:
- SELECT device_id, email_client
FROM machines;
- What email client is returned in the third row?
- Email Client 2

3. Now, you need information on the operating systems used on various devices and their last patch date.
Complete the query to return only the device_id, operating_system, and OS_patch_date columns from the machines table. Replace X, Y, and Z with the columns that you need to return:
- SELECT device_id, operating_system, OS_patch_date
FROM machines;
- output:
+--------------+------------------+---------------+
| device_id    | operating_system | OS_patch_date |
+--------------+------------------+---------------+
| a184b775c707 | OS 1             | 2021-09-01    |
| a192b174c940 | OS 2             | 2021-06-01    |
| a305b818c708 | OS 3             | 2021-06-01    |
| a317b635c465 | OS 1             | 2021-03-01    |
| a320b137c219 | OS 2             | 2021-03-01    |

Task 2. Investigate login activity
In this task, you need to analyze the information from the log_in_attempts table to determine if any unusual activity has occurred.

First, you need to investigate the locations where login attempts were made to ensure that they’re in expected areas (the United States, Canada, or Mexico).

1. Write a SQL query to select the event_id and country columns from the log_in_attempts table.
- SELECT event_id, country
FROM log_in_attempts;

Were any login attempts made from Australia?
- no

Next, you need to check if login attempts were made outside of the organization's working hours.
2. Write a SQL query that selects the username, login_date, and login_time columns from the log_in_attempts table.
- SELECT username, login_date, login_time
FROM log_in_attempts;

What username is returned in the fifth row?
- jrafael

+----------+------------+------------+
| username | login_date | login_time |
+----------+------------+------------+
| jrafael  | 2022-05-09 | 04:56:27   |
| apatel   | 2022-05-10 | 20:27:27   |
| dkot     | 2022-05-09 | 06:47:41   |
| dkot     | 2022-05-08 | 02:00:39   |
| jrafael  | 2022-05-11 | 03:05:59   |
| arutley  | 2022-05-12 | 17:00:59   |
| eraab    | 2022-05-11 | 01:45:14   |

Now, you need to get a complete picture of all login attempts.
3. Write a SQL query that selects all columns from the log_in_attempts table, using a single symbol after the SELECT keyword.
- SELECT *
FROM log_in_attempts;


Task 3. Order login attempts data
In this task, you need to use the ORDER BY keyword. You'll sequence the data that your query returns according to the login date and time.

First, you need to sort the information by date.

1. Run the following query, which orders log_in_attempts data by login_date:
- SELECT *
FROM log_in_attempts
ORDER BY login_date;

What are the username and login date of the first record returned?
- Ivelasco on 2022-05-08

Now, you need to further organize the previous results by ordering them by login_time.

2. Modify the query from the previous step by adding the login time to the ORDER BY clause. You must replace X with the appropriate column name:
- SELECT *
FROM log_in_attempts
ORDER BY login_date, login_time;

What are the username and login time of the first record returned by the above query?
- bsand at 00:19:11
