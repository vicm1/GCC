Task 1
In your work as an analyst, imagine that you're provided a list of the number of failed login attempts per month, as follows:

119, 101, 99, 91, 92, 105, 108, 85, 88, 90, 264, and 223.

This list is organized in chronological order of months (January, February, March, April, May, June, July, August, September, October, November, and December).

This list is stored in a variable named failed_login_list.

In this task, use a built-in Python function to order the list. You'll pass the call to the function that sorts the list directly into the print() function. This will allow you to display and examine the result.

Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell.

# Assign `failed_login_list` to the list of the number of failed login attempts per month
​
failed_login_list = [119, 101, 99, 91, 92, 105, 108, 85, 88, 90, 264, 223]
​
# Sort `failed_login_list` in ascending numerical order and display the result
​
print(sorted(failed_login_list))

- [85, 88, 90, 91, 92, 99, 101, 105, 108, 119, 223, 264]

Question 1
What do you observe from the output above? Do you notice any outlying numbers that indicate an increase in the failed number of login attempts?

- It almost doubles in failed number of login attempts after 119.

Task 2
Now, you'll want to isolate the highest number of failed login attempts so you can later investigate information about the month when that highest value occurred.

You'll use the function that returns the largest numeric element from a list. Then, you'll pass this function into the print() function to display the result. This will allow you to determine which month to investigate further.

Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell.

failed_login_list
# Assign `failed_login_list` to the list of the number of failed login attempts per month
​
failed_login_list = [119, 101, 99, 91, 92, 105, 108, 85, 88, 90, 264, 223]
​
# Determine the highest number of failed login attempts from `failed_login_list` and display the result
​
print(max(failed_login_list))

- 264

To determine the highest number of failed login attempts from failed_login_list, use the max() function.

This is a built-in Python function that takes in a sequence, identifies the maximum value from the sequence and returns the result.


Question 2
What do you observe from the output above?

- 264 is the most failed login attempts.

Task 3
In your work as an analyst, you'll first define a function that displays a message about how many login attempts a user has made that day.

In this task, define a function named analyze_logins() that takes in two parameters, username and current_day_logins. Every time this function is called, it should display a message about the number of login attempts the user has made that day.

Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell. Note that the code cell will contain only a function definition, so running it will not produce an output.

# Define a function named `analyze_logins()` that takes in two parameters, `username` and `current_day_logins`
​
def analyze_logins(username, current_day_logins):
​
    # Display a message about how many login attempts the user has made that day
​
    print("Current day login total for", username, "is", current_day_logins)
​
​
Now that you've defined the analyze_logins() function, call it to test out how it behaves.

Call analyze_logins() with the arguments "ejones" and 9.

Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell.

"ejones", 9
# Define a function named `analyze_logins()` that takes in two parameters, `username` and `current_day_logins`
​
def analyze_logins(username, current_day_logins):
​
    # Display a message about how many login attempts the user has made that day
​
    print("Current day login total for", username, "is", current_day_logins)
​
# Call `analyze_logins()`
​
analyze_logins("ejones", 9)
​
- Current day login total for ejones is 9

Question 3
What does this function display? Would the output vary for different users?

- The function displays the username and how many logins they did that day.The output would vary for different users depending on their username and login.

Task 5
Now, you'll need to expand this function so that it also provides the average number of login attempts made by the user on that day. Doing this will require incorporating a third parameter into the function definition.

In this task, add a parameter called average_day_logins. The code will use this parameter to display an additional message. The additional message will convey the average login attemps made by the user on that day. Then, call the function with the same first and second arguments as used in Task 4 and a third argument of 3.

Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell.

"ejones", 9, 3
# Define a function named `analyze_logins()` that takes in three parameters, `username`, `current_day_logins`, and `average_day_logins`
​
def analyze_logins(username, current_day_logins, average_day_logins):
​
    # Display a message about how many login attempts the user has made that day
​
    print("Current day login total for", username, "is", current_day_logins)
​
    # Display a message about average number of login attempts the user has made that day
​
    print("Average logins per day for", username, "is", average_day_logins)
​
# Call `analyze_logins()`
​
analyze_logins("ejones", 9, 3)

- Current day login total for ejones is 9
Average logins per day for ejones is 3

Task 6
In this task, you'll further expand the function. Include a calculation to get the ratio of the logins made on the current day to the logins made on an average day. Store this in a new variable named login_ratio. The function displays an additional message that uses this variable.

Note that if average_day_logins is equal to 0, then dividing current_day_logins by average_day_logins will cause an error. Due to the error, Python will display the following message: ZeroDivisionError: division by zero. For this activity, assume that all users will have logged in at least once before. This means that their average_day_logins will be greater than 0, and the function will not involve dividing by zero.

After defining the function, call the function with the same arguments that you used in the previous task.

Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell.

# Define a function named `analyze_logins()` that takes in three parameters, `username`, `current_day_logins`, and `average_day_logins`
​
def analyze_logins(username, current_day_logins, average_day_logins):
​
    # Display a message about how many login attempts the user has made that day
​
    print("Current day login total for", username, "is", current_day_logins)
​
    # Display a message about average number of login attempts the user has made that day
​
    print("Average logins per day for", username, "is", average_day_logins)
​
    # Calculate the ratio of the logins made on the current day to the logins made on an average day, storing in a variable named `login_ratio`
​
    login_ratio = current_day_logins/average_day_logins
​
    # Display a message about the ratio
​
    print(username, "logged in", login_ratio, "times as much as they do on an average day.")
​
# Call `analyze_logins()`
​
analyze_logins("ejones", 9, 3)
​
- Current day login total for ejones is 9
Average logins per day for ejones is 3
ejones logged in 3.0 times as much as they do on an average day.

Question 4
What does this version of the analyze_logins() function display? Would the output vary for different users?

- This output displays the current day login total, average logins, and the ratio of logins/avglogins. The output would vary by different users.

Task 7
You'll continue working with the analyze_logins() function and add a return statement to it. Return statements allow you to send information back to the function call.

In this task, use the return keyword to output the login_ratio from the function, so that it can be used later in your work.

You'll call the function with the same arguments used in the previous task and store the output from the function call in a variable named login_analysis. You'll then use a print() statement to display the saved information.

Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell.

login_analysis = analyze_logins("ejones", 9, 3)
# Define a function named `analyze_logins()` that takes in three parameters, `username`, `current_day_logins`, and `average_day_logins`
​
def analyze_logins(username, current_day_logins, average_day_logins):
​
    # Display a message about how many login attempts the user has made that day
​
    print("Current day login total for", username, "is", current_day_logins)
​
    # Display a message about average number of login attempts the user has made that day
​
    print("Average logins per day for", username, "is", average_day_logins)
​
    # Calculate the ratio of the logins made on the current day to the logins made on an average day, storing in a variable named `login_ratio`
​
    login_ratio = current_day_logins / average_day_logins
​
    # Return the ratio
​
    return login_ratio
​
# Call `analyze_logins() and store the output in a variable named `login_analysis`
​
login_analysis = analyze_logins("ejones", 9, 3)
​
# Display a message about the `login_analysis`
​
print("ejones", "logged in", login_analysis, "times as much as they do on an average day.")
​
- Current day login total for ejones is 9
Average logins per day for ejones is 3
ejones logged in 3.0 times as much as they do on an average day.

Question 5
How does this version of the analyze_logins() function compare to the previous versions?

- Login_analysis is created as a variable to hold analyze_logins().

Task 8
In this task, you'll use the value of login_analysis in a conditional statement. When the value of login_analysis is greater than or equal to 3, then the login activity will require further investigation, and an alert will be displayed. Incorporate this condition to complete the conditional statement in the code.

Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell.

:
# Define a function named `analyze_logins()` that takes in three parameters, `username`, `current_day_logins`, and `average_day_logins`
​
def analyze_logins(username, current_day_logins, average_day_logins):
​
    # Display a message about how many login attempts the user has made that day
​
    print("Current day login total for", username, "is", current_day_logins)
​
    # Display a message about average number of login attempts the user has made that day
​
    print("Average logins per day for", username, "is", average_day_logins)
​
    # Calculate the ratio of the logins made on the current day to the logins made on an average day, storing in a variable named `login_ratio`
​
    login_ratio = current_day_logins / average_day_logins
​
    # Return the ratio
​
    return login_ratio
​
# Call `analyze_logins() and store the output in a variable named `login_analysis`
​
login_analysis = analyze_logins("ejones", 9, 3)
​
# Conditional statement that displays an alert about the login activity if it's more than normal
​
if login_analysis >= 3:
    print("Alert! This account has more login activity than normal.")

- Current day login total for ejones is 9
Average logins per day for ejones is 3
Alert! This account has more login activity than normal.
