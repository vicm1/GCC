Task 1. Get the current directory information
1. Display the working directory
Use pwd command, /home
2. Display the names of the files and directories in the current working directory. How many directories does the current working directory contain?
/home/analyst using pwd
Four directories, those being logs, projects, reports, and temp

Task 2. Change directory and list the subdirectories
1. Navigate to the /home/analyst/reports directory
cd reports -> from home to reports directory

2. Display the files and subdirectories in the /home/analyst/reports
ls reports -> users

Task 3. Locate and read the contents of a file
1.  Navigate to the /home/analyst/reports/users directory.
2. List the files in the current directory
3. Display the contents of Q1_added_users.txt file
What department does the employee with the username aezra work?
- Human resources
What is the employee_id of the user mreed in the information Technology deparmtent?
- 1104

Task 4. Navigate to a directory and locate a files
1. Navigate to the /home/analyst/logs directory
2. Display the name of the file it contains
3. Display the first 10 lines of this files
How many warning messages are in the first 10 lines of the server_logs.txt file.
- Three

Linux Bash CMD:
analyst@dfb7cc436352:~$ ls
logs  projects  reports  temp
analyst@dfb7cc436352:~$ cd
analyst@dfb7cc436352:~$ ls
logs  projects  reports  temp
analyst@dfb7cc436352:~$ /home
-bash: /home: Is a directory
analyst@dfb7cc436352:~$ ls home
ls: cannot access 'home': No such file or directory
analyst@dfb7cc436352:~$ ls /home
analyst  student
analyst@dfb7cc436352:~$ ls
logs  projects  reports  temp
analyst@dfb7cc436352:~$ cd /home
analyst@dfb7cc436352:/home$ ls
analyst  student
analyst@dfb7cc436352:/home$ cd analust
-bash: cd: analust: No such file or directory
analyst@dfb7cc436352:/home$ cd analyst
analyst@dfb7cc436352:~$ ls
logs  projects  reports  temp
analyst@dfb7cc436352:~$ ls
logs  projects  reports  temp
analyst@dfb7cc436352:~$ pwd
/home/analyst
analyst@dfb7cc436352:~$ /analyst
-bash: /analyst: No such file or directory
analyst@dfb7cc436352:~$ /home
-bash: /home: Is a directory
analyst@dfb7cc436352:~$ /home/analyst
-bash: /home/analyst: Is a directory
analyst@dfb7cc436352:~$ ls reports
users
analyst@dfb7cc436352:~$ cd reports
analyst@dfb7cc436352:~/reports$ ls
users
analyst@dfb7cc436352:~/reports$ cd
analyst@dfb7cc436352:~$ ls
logs  projects  reports  temp
analyst@dfb7cc436352:~$ cd users
-bash: cd: users: No such file or directory
analyst@dfb7cc436352:~$ cd reports
analyst@dfb7cc436352:~/reports$ ls
users
analyst@dfb7cc436352:~/reports$ cd users
analyst@dfb7cc436352:~/reports/users$ ls
Q1_added_users.txt  Q1_deleted_users.txt
analyst@dfb7cc436352:~/reports/users$ cat Q1_added_users.txts
cat: Q1_added_users.txts: No such file or directory
analyst@dfb7cc436352:~/reports/users$ cat Q1_added_users.txt
employee_id  username  department
1001         bmoreno   Marketing
1026         apatel    Human Resources
1041         cgriffin  Sales
1104         mreed     Information Technology
1177         aezra     Human Resources
1188         noshiro   Finance
analyst@dfb7cc436352:~/reports/users$ ls
Q1_added_users.txt  Q1_deleted_users.txt
analyst@dfb7cc436352:~/reports/users$ cd
analyst@dfb7cc436352:~$ ls
logs  projects  reports  temp
analyst@dfb7cc436352:~$ cd logs
analyst@dfb7cc436352:~/logs$ ls
server_logs.txt
analyst@dfb7cc436352:~/logs$ head server_logs.txt
2022-09-28 13:55:55 info    User logged on successfully
2022-09-28 13:56:22 error   The password is incorrect
2022-09-28 13:56:48 warning The file storage is 75% full
2022-09-28 15:55:55 info    User logged on successfully
2022-09-28 15:56:22 error   The username is incorrect
2022-09-28 15:56:48 warning The file storage is 90% full
2022-09-28 16:55:55 info    User navigated to settings page
2022-09-28 16:56:22 error   The password is incorrect
2022-09-28 16:56:48 warning The current user’s password expires in 15 days
2022-09-29 13:55:55 info    User logged on successfully
analyst@dfb7cc436352:~/logs$ 
