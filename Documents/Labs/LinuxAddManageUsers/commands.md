Task 1. Add a new user
A new employee has joined the Research department. In this task, you must add them to the system. The username assigned to them is researcher9.
1. Write a command to add a user called researcher9 to the system.
Next, you need to add the new user to the research_team group.
- sudo useradd researcher9
2. Use the usermod command and -g option to add researcher9 to the research_team group as their primary group.
- sudo usermod -g research_team researcher9

Task 2. Assign File ownership
The new employee, researcher9, will take responsibility for project_r. In this task, you must make them the owner of the project_r.txt file.
The project_r.txt file is located in the /home/researcher2/projects directory, and owned by the researcher2 user.
1. Use the chown command to make researcher9 the owner of /home/researcher2/projects/project_r.txt.
- sudo chown researcher9 /home/researcher2/projects/project_r.txt

Task 3. Add the user to a secondary group
A couple of months later, this employee's role at the organization has changed, and they are working in both the Research and the Sales departments.
In this task, you must add researcher9 to a secondary group (sales_team). Their primary group is still research_team.

1. Use the usermod command with the -a and -G options to add researcher9 to the sales_team group as a secondary group.
- sudo usermod -a -G sales_team researcher9

Task 4. Delete a user
A year later, researcher9, decided to leave the company. In this task, you must remove them from the system.

1. Run a command to delete researcher9 from the system:
- sudo userdel researcher9
This command will output the following message:
Userdel: Group researcher9 not removed because it is not the primary group of user researcher9.
2. Run the following command to delete the researcher9 group that is no longer required:
- sudo groupdel researcher9
