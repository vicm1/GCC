Task 1. Retrieve login attempts after a certain date
In this task, you need to investigate a recent security incident. To do this, you need to gather information about login attempts made after a certain date.

1. Write a SQL query to retrieve data for login attempts made after '2022-05-09'.
- SELECT *
FROM log_in_attempts
WHERE login_date > '2022-05-09';

Now, based on your first query, you find a need to expand the date range to include 2022-05-09 in your search.

2. Write a SQL query to retrieve data for login attempts that were made on or after '2022-05-09'.
- SELECT *
    -> FROM log_in_attempts       
    -> WHERE login_date >= '2022-05-09';

Task 2. Retrieve logins in a date range
In this task, you need to narrow the focus of the search. Login attempts made after 2022-05-11 shouldn't be included. Use the BETWEEN and AND operators to return results between '2022-05-09' and '2022-05-11'.

1. Write a query retrieve the required records.
- SELECT *
FROM log_in_attempts
WHERE login_date BETWEEN '2022-05-09' AND '2022-05-11';

Task 3. Investigate logins at certain times
In this task, you need to investigate logins that were made at certain times. To do this, filter the data in the log_in_attempts table by login time (login_time).

First, your organization's typical work hours begin at 07:00:00. Retrieve all login attempts made before 07:00:00 to learn more about the users who are logging in outside of typical hours.

1. Write a SQL query to retrieve data for login attempts made before '07:00:00'.
- SELECT *
FROM log_in_attempts
WHERE login_time < '07:00:00';

The query in the previous step returned more results than required.

2. Modify the query to return logins between '06:00:00' and '07:00:00'.
- SELECT *
FROM log_in_attempts
WHERE login_time BETWEEN '06:00:00' AND '07:00:00';


Task 4. Investigate logins by event ID
In this task, you need to investigate login attempts based on event ID numbers. With this query, you want to return only the event_id, username, and login_date fields from the log_in_attempts table.

1. Write a query to return login attempts with event_id greater than or equal to 100.
- SELECT *
FROM log_in_attempts
WHERE event_id >= 100;

The query in the previous step returned more data than required.

2. Modify the query to return only login attempts with event_id between 100 and 150.
- SELECT *
FROM log_in_attempts
WHERE event_id BETWEEN 100 AND 150;
