Task 1. Check file and directory details
In this task, you must explore the permissions of the projects directory and the files it contains. The lab starts with /home/researcher2 as the current working directory. This is because you're changing permissions for files and directories belonging to the researcher2 user.

1. Navigate to the projects directory.
- cd projects
2. List the contents and permissions of the projects directory.
- ls -l
researcher2@e76cefa6493a:~/projects$ ls -l
total 20
drwx--x--- 2 researcher2 research_team 4096 Oct  4 19:16 drafts
-rw-rw-rw- 1 researcher2 research_team   46 Oct  4 19:16 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Oct  4 19:16 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_t.txt

What is the name of the group that owns the files in the projects directory?
- research_team

3. Check whether any hidden files exist in the projects directory.
- .project_x.txt

Task 2. Change file permissions
1. Check whether any files in the projects directory have write permissions for the owner type of other.
Which file grants other users write permissions?
- project_k.txt

2. Change the permissions of the file identified in the previous step so that the owner type of other doesn’t have write permissions.
- chmod o-w project_k.txt
- -rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_k.txt

3. The file project_m.txt is a restricted file and should not be readable or writable by the group or other; only the user should have these permissions on this file. List the contents and permissions of the current directory and check if the group has read or write permissions.
What are the group permissions on the project_m.txt file?
- Read only

4. Use the chmod command to change permissions of the project_m.txt file so that the group doesn’t have read or write permissions.
- chmod g-r project_m.txt
- -rw------- 1 researcher2 research_team   46 Oct  4 19:16 project_m.txt

Task 3. Change file permissions on a hidden file
In this task, you must determine if a hidden file has incorrect permissions and then change the permissions as needed. This action will further remove unauthorized access and strengthen security on the system.

The file .project_x.txt is a hidden file that has been archived and should not be written to by anyone. (The user and group should still be able to read this file.)
1. Check the permissions of the hidden file .project_x.txt and answer the question that follows.
Which owner type has the incorrect write permissions?
- The user and the group

2. Change the permissions of the file .project_x.txt so that both the user and the group can read, but not write to, the file.
- chmod u-w,g-w,g+r .project_x.txt
- -r--r----- 1 researcher2 research_team   46 Oct  4 19:16 .project_x.txt

Task 4. Change directory permissions
In this task, you must change the permissions of a directory. First, you’ll check the group permissions of the /home/researcher2/projects/drafts directory and then modify the permissions as required. (You should be in the projects directory while managing the permissions of its subdirectory drafts.)

Only the researcher2 user should be allowed to access the drafts directory and its contents. (This means that only researcher2 should have execute privileges.)

1. Check the permissions of the drafts directory and answer the following question.
Does the group have permissions set to access the drafts directory and its contents?
- yes

2. Remove the execute permission for the group from the drafts directory.
- chmod g-x drafts

researcher2@e76cefa6493a:~$ ls
projects
researcher2@e76cefa6493a:~$ cd projects
researcher2@e76cefa6493a:~/projects$ ls
drafts  project_k.txt  project_m.txt  project_r.txt  project_t.txt
researcher2@e76cefa6493a:~/projects$ ls -l
total 20
drwx--x--- 2 researcher2 research_team 4096 Oct  4 19:16 drafts
-rw-rw-rw- 1 researcher2 research_team   46 Oct  4 19:16 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Oct  4 19:16 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_t.txt
researcher2@e76cefa6493a:~/projects$ -ls -la
-bash: -ls: command not found
researcher2@e76cefa6493a:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 19:16 .
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 20:00 ..
-rw--w---- 1 researcher2 research_team   46 Oct  4 19:16 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Oct  4 19:16 drafts
-rw-rw-rw- 1 researcher2 research_team   46 Oct  4 19:16 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Oct  4 19:16 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_t.txt
researcher2@e76cefa6493a:~/projects$ chmod o-w project_k.txt
researcher2@e76cefa6493a:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 19:16 .
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 20:00 ..
-rw--w---- 1 researcher2 research_team   46 Oct  4 19:16 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Oct  4 19:16 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Oct  4 19:16 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_t.txt
researcher2@e76cefa6493a:~/projects$ chmod g-r project_m.txt
researcher2@e76cefa6493a:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 19:16 .
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 20:00 ..
-rw--w---- 1 researcher2 research_team   46 Oct  4 19:16 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Oct  4 19:16 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_k.txt
-rw------- 1 researcher2 research_team   46 Oct  4 19:16 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_t.txt
researcher2@e76cefa6493a:~/projects$ chmod u-w,g-w,g+r .project_x.txt
researcher2@e76cefa6493a:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 19:16 .
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 20:00 ..
-r--r----- 1 researcher2 research_team   46 Oct  4 19:16 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Oct  4 19:16 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_k.txt
-rw------- 1 researcher2 research_team   46 Oct  4 19:16 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_t.txt
researcher2@e76cefa6493a:~/projects$ ls
drafts  project_k.txt  project_m.txt  project_r.txt  project_t.txt
researcher2@e76cefa6493a:~/projects$ chmod g-x drafts
researcher2@e76cefa6493a:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 19:16 .
drwxr-xr-x 3 researcher2 research_team 4096 Oct  4 20:00 ..
-r--r----- 1 researcher2 research_team   46 Oct  4 19:16 .project_x.txt
drwx------ 2 researcher2 research_team 4096 Oct  4 19:16 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_k.txt
-rw------- 1 researcher2 research_team   46 Oct  4 19:16 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Oct  4 19:16 project_t.txt
researcher2@e76cefa6493a:~/projects$
