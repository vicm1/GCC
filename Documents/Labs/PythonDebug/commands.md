Task 1
The following code cell contains a syntax error. In this task, you'll run the code, identify why the error is occuring, and modify the code to resolve it. (To ensure that it has been resolved, run the code again to check if it now functions properly.)

:
"# For loop that iterates over a range of numbers
"# and displays a message each iteration
​
for i in range(10):
    print("Connection cannot be established")

- Connection cannot be established
Connection cannot be established
Connection cannot be established
Connection cannot be established
Connection cannot be established
Connection cannot be established
Connection cannot be established
Connection cannot be established
Connection cannot be established
Connection cannot be established

Question 1
What happens when you run the code before modifying it? How can you fix this?

- Gives me a syntax error, can fix this by adding a colon after the for statement.

Task 2
In the following code cell, you're provided a list of usernames. There is an issue with the syntax. In this task, you'll run the cell, observe what happens, and modify the code to fix the issue.

"# Assign `usernames_list` to a list of usernames
​
usernames_list = ["djames", "jpark", "tbailey", "zdutchma", "esmith", "srobinso", "dcoleman", "fbautist"]
​
"# Display `usernames_list`
​
print(usernames_list)

- ['djames', 'jpark', 'tbailey', 'zdutchma', 'esmith', 'srobinso', 'dcoleman', 'fbautist']

Question 2
What happens when you run the code before modifying it? How can you fix it?

- Syntax error, fix it by adding a comma after one of the usernames.

Task 3
In the following code cell, there is a syntax error. Your task is to run the cell, identify what is causing the error, and fix it.

)
"# Display a message in upper case
​
print("update needed".upper())
- UPDATE NEEDED

Question 3
What happens when you run the code before modifying it? What is causing the syntax error? How can you fix it?

- Says syntax needed, it's missing a paranthesis at the end of print so add it to fix it.

Task 4
In the following code cell, you're provided a usernames_list, a username, and code that determines whether the username is approved. There are two syntax errors and one exception. Your task is to find them and fix the code. A helpful debugging strategy is to focus on one error at a time and run the code after fixing each one.

"# Assign `usernames_list` to a list of usernames that represent approved users
​
usernames_list = ["djames", "jpark", "tbailey", "zdutchma", "esmith", "srobinso", "dcoleman", "fbautist"]
​
"# Assign `username` to a specific username
​
username = "esmith"
​
"# For loop that iterates over the elements of `usernames_list` and determines whether each element corresponds to an approved user
​
for name in usernames_list:
​
    # Check if `name` matches `username`
    # If it does match, then display a message accordingly
​
    if name == username:
        print("The user is an approved user")
The user is an approved user

Question 4
What happens when you run the code before modifying it? What is causing the errors? How can you fix it?

- Get multiple errors, two syntax errors and one exception. To fix the first two syntax errors change the = in if to ==, and for the other one add the correct variable name, usernames_list. The one exception is to indent the print in the if statement.

Task 5
In this task, you'll examine the following code and identify the type of error that occurs. Then, you'll adjust the code to fix the error.

4
"# Assign `usernames_list` to a list of usernames
​
usernames_list = ["elarson", "bmoreno", "tshah", "sgilmore", "eraab"]
​
"# Assign `username` to a specific username
​
username = "eraab"
​
"# Determine whether `username` is the final username in `usernames_list`
"# If it is, then display a message accordingly
​
if username == usernames_list[4]:
    print("This username is the final one in the list.")

- This username is the final one in the list.

Question 5
What happens when you run the code before modifying it? What type of error is this? How can you fix it?

- Error that the index is out of range. Index error, fix it by changing 5 to a 4 so it will be in bound.

Task 6
In this task, you'll examine the following code. The code imports a text file into Python, reads its contents, and stores the contents as a list in a variable named ip_addresses. It then removes elements from ip_addresses if they are in remove_list. There are two errors in the code: first a syntax error and then an exception related to a string method. Your goal is to find these errors and fix them.

"# Assign `import_file` to the name of the text file
​
import_file = "allow_list.txt"
​
"# Assign `remove_list` to a list of IP addressess that are no longer allowed to access the network
​
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]
​
"# With statement that reads in the text file and stores its contents as a list in `ip_addresses`
​
with open(import_file, "r") as file:
    ip_addresses = file.read()
​
"# Convert `ip_addresses` from a string to a list
​
ip_addresses = ip_addresses.split()
​
"# For loop that iterates over the elements in `remove_list`,
"# checks if each element is in `ip_addresses`,
"# and removes each element that corresponds to an IP address that is no longer allowed
​
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)
​
"# Display `ip_addresses` after the removal process
​
print(ip_addresses)
- ['ip_address', '192.168.25.60', '192.168.205.12', '192.168.6.9', '192.168.52.90', '192.168.90.124', '192.168.186.176', '192.168.133.188', '192.168.203.198', '192.168.218.219', '192.168.52.37', '192.168.156.224', '192.168.60.153', '192.168.69.116']

Question 6
What happens when you run the code before modifying it? What is causing the errors? How can you fix them?

- Two syntax errors, first can be fixed by adding a colon at the end of with and fix the split() syntax.

Task 7
In this final task, there are three operating systems: OS 1, OS 2, and OS 3. Each operating system needs a security patch by a specific date. The patch date for OS 1 is "March 1st", the patch date for OS 2 is "April 1st", and the patch date for OS 3 is "May 1st".

The following code stores one of these operating systems in a variable named system. Then, it uses conditionals to output the patch date for this operating system.

However, this code has logic errors. Your goal is to assign the system variable to different values, run the code to examine the output, identify the error, and fix it.

"# Assign `system` to a specific operating system as a string
​
system = "OS 2"
​
"# Assign `patch_schedule` to a list of patch dates in order of operating system
​
patch_schedule = ["March 1st", "April 1st", "May 1st"]
​
"# Conditional statement that checks which operating system is stored in `system` and displays a message showing the corresponding patch date
​
if system == "OS 1":
    print("Patch date:", patch_schedule[0])
​
elif system == "OS 2":
    print("Patch date:", patch_schedule[1])
​
elif system == "OS 3":
    print("Patch date:", patch_schedule[2])

- Patch date: April 1st

Question 7
What happens when you run the code before modifying it? What is causing the logic errors? How can you fix them?

- Get the wrong date for the patch update, to fix it change the index to start from 0.
