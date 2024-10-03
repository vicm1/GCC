Task 1. Create a new directory
First, you must create a dedicated subdirectory called logs, which will be used to store all future log files.
1. Create a new subdirectory called logs in the /home/analyst directory.
- cd /home/analyst
2. List the contents of the /home/analyst directory to confirm that you’ve successfully created the new logs subdirectory.
- mkdir logs

Task 2. Remove Directory
1. Remove the /home/analyst/temp directory.
- cd /home/analyst
2. List the contents of the /home/analyst directory to confirm that you have removed the temp subdirectory.
- rmdir temp

Task 3. Move a file
The Q3patches.txt file contains notes taken on third-quarter patches and is now in the correct reporting format.
You must move the  Q3patches.txt file from the notes directory to the reports directory.
1. Navigate to the /home/analyst/notes directory.
- cd /home/analyst/notes
2. Move the Q3patches.txt file from the /home/analyst/notes directory to the /home/analyst/reports directory.
- mv Q3patches.txt /home/analyst/reports
3. List the contents of the /home/analyst/reports directory to confirm that you have moved the file successfully.
- Q1patches.txt, Q2patches.txt, Q3patches.txt

Task 4. Remove a file
Next, you must delete an unused file called tempnotes.txt from the /home/analyst/notes directory.
1. Remove the tempnotes.txt file from the /home/analyst/notes directory.
- rm tempnotes.txt
2. List the contents of the /home/analyst/notes directory to confirm that you’ve removed the file successfully.
- No files are listed in the notes directory.

Task 5. Create a new file
Now, you must create a file named tasks.txt in the /home/analyst/notes directory that you’ll use to document completed tasks.
1. Use the touch command to create an empty file called tasks.txt in the /home/analyst/notes directory.
- touch tasks.txt
2. List the contents of the /home/analyst/notes directory to confirm that you have created a new file.
- tasks.txt

Task 6. Edit a file
Finally, you must use the nano text editor to edit the tasks.txt file and add a note describing the tasks you’ve completed.
1. Using the nano text editor, open the tasks.txt file that is located in the /home/analyst/notes directory.
- nano tasks.txt
2. Copy and paste the following text into the text input area of the nano editor:
-   Completed tasks
  Managed file structure in /home/analyst
3. Press CTRL+X to exit the nano text editor.
This triggers a prompt asking Save modified bufferer?
4. Press Y to confirm that you want to save the new data to your file. (Answering "no" will discard changes.)
5. Press ENTER to confirm that File Name to Write is tasks.txt.
6. Use the clear command to clear the Bash shell window and remove any traces of the nano text input area.
7. Display the contents of the tasks.txt file to confirm that it contains the updated task details.
