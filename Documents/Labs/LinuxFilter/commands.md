Task 1. Search for error messages in a log files
In this task, you must navigate to the /home/analyst/logs directory and report on the error messages in the server_logs.txt file. You’ll do this by using grep to search the file and output only the entries that are for errors.
1. Navigate to the /home/analyst/logs directory.
- cd /home/analyst/logs
2. Use grep to filter the server_logs.txt file, and return all lines containing the text string error.
- grep error server_logs.txt
How many files in the /home/analyst/reports/users subdirectory contain “Q1” in their names?
Three, ls /home/analyst/reports/users | grep Q1
3. List the files that contain the word access in their names.
- How many files in the /home/analyst/reports/users directory contain “access” in their names?
- ls /home/analyst/reports/users | grep access

Task 3. Search more file contents
1. Display the files in the /home/analyst/reports/users directory.
2. Search the Q2_deleted_users.txt file for the username jhill.
- ls /home/analyst/reports/users | grep jhill Q2_deleted_users.txt
3. Search the Q4_added_users.txt file to list the users who were added to the Human Resources department.
- ls /home/analyst/reports/users | grep "Human Resources" Q4_added_users.txt
4. How many users were added to the Human Resources department in quarter 4?
- 2
