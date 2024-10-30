Task 1. Read the contents of a file
The lab starts in your home directory, /home/analyst, as the current working directory.

In this task, you need to explore the contents of your home directory and read the contents of a file to get further instructions.

Use the ls command to list the files in the current working directory.
Two files, Q1.encrypted and README.txt, and a subdirectory, caesar, are listed:
Q1.encrypted  README.txt caesar

The README.txt file contains an important message with instructions you need to follow.

Use the cat command to list the contents of the README.txt file.
The message in the README.txt file advises that the caesar subdirectory contains a hidden file.

In the next task, you’ll need to find the hidden file and solve the Caesar cipher that protects it. The file contains instructions on how to recover your data.

Click Check my progress to verify that you have completed this task correctly.

Task 2. Find a hidden file
In this task, you need to find a hidden file in your home directory and decrypt the Caesar cipher it contains. This task will enable you to complete the next task.

1. First, use the cd command to change to the caesar subdirectory of your home directory:
- cd caesar

2. Use the ls -a command to list all files, including hidden files, in your home directory.

Hidden files in Linux can be identified by their name starting with a period (.).

Use the cat command to list the contents of the .leftShift3 file.
The message in the .leftShift3 file appears to be scrambled. This is because the data has been encrypted using a Caesar cipher. This cipher can be solved by shifting each alphabet character to the left or right by a fixed number of spaces. In this example, the shift is three letters to the left. Thus "d" stands for "a", and "e" stands for "b".

Hidden files in Linux can be identified by their name starting with a period (.).

3. Use the cat command to list the contents of the .leftShift3 file.
The message in the .leftShift3 file appears to be scrambled. This is because the data has been encrypted using a Caesar cipher. This cipher can be solved by shifting each alphabet character to the left or right by a fixed number of spaces. In this example, the shift is three letters to the left. Thus "d" stands for "a", and "e" stands for "b".

4. You can decrypt the Caesar cipher in the .leftshift3 file by using the following command:
- cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"

Task 3. Decrypt a file
Now that you have solved the Caesar cipher, in this task you need to use the command revealed in .leftshift3 to decrypt a file and recover your data so you can read the message it contains.

Use the exact command revealed in the previous task to decrypt the encrypted file:
- openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute

Although you don't need to memorize this command, to help you better understand the syntax used, let's break it down.

In this instance, the openssl command reverses the encryption of the file with a secure symmetric cipher, as indicated by AES-256-CBC. The -pbkdf2 option is used to add extra security to the key, and -a indicates the desired encoding for the output. The -d indicates decrypting, while -in specifies the input file and -out specifies the output file. The -k specifies the password, which in this example is ettubrute.

2. Use the ls command to list the contents of your current working directory again.
The new file Q1.recovered in the directory listing is the decrypted file and contains a message.

3. Use the cat command to list the contents of the Q1.recovered file.

cmd:
analyst@8ff24c0cf742:~$ ls
Q1.encrypted  README.txt  caesar
analyst@8ff24c0cf742:~$ cat README.txt
Hello,
All of your data has been encrypted. To recover your data, you will need to solve a cipher. To get started look for a hidden file in the caesar subdirectory.
analyst@8ff24c0cf742:~$ cd caesar
analyst@8ff24c0cf742:~/caesar$ ls
analyst@8ff24c0cf742:~/caesar$ ls -a
.  ..  .leftShift3
analyst@8ff24c0cf742:~/caesar$ cat .leftshit3
cat: .leftshit3: No such file or directory
analyst@8ff24c0cf742:~/caesar$ cat .leftshift3
cat: .leftshift3: No such file or directory
analyst@8ff24c0cf742:~/caesar$ cat .leftShift3
Lq rughu wr uhfryhu brxu ilohv brx zloo qhhg wr hqwhu wkh iroorzlqj frppdqg:

rshqvvo dhv-256-fef -sengi2 -d -g -lq T1.hqfubswhg -rxw T1.uhfryhuhg -n hwwxeuxwh
analyst@8ff24c0cf742:~/caesar$ cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"
In order to recover your files you will need to enter the following command:

openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
analyst@8ff24c0cf742:~/caesar$ cd ~
analyst@8ff24c0cf742:~$ openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
analyst@8ff24c0cf742:~$ ls
Q1.encrypted  Q1.recovered  README.txt  caesar
analyst@8ff24c0cf742:~$ cd q1.recovered
-bash: cd: q1.recovered: No such file or directory
analyst@8ff24c0cf742:~$ cd Q1.recovered
-bash: cd: Q1.recovered: Not a directory
analyst@8ff24c0cf742:~$ cat Q1.recovered
If you are able to read this, then you have successfully decrypted the classic cipher text. You recovered the encryption key that was used to encrypt this file. Great work!
analyst@8ff24c0cf742:~$ cat Q1.encrypted
U2FsdGVkX1/nxHZY2p53/6gRmQ9alkNrVwOwPOgpTeB09rdnvKnydLPQsnOYHjgR
42Mwdv0ye94Im+u100Fl2+Bx3SHjJ7wZjOxA7Jew1x7g3LcRsRnFcFLyfAnn0f3u
xMIH/y+Y4HfVb6NUFueXM43M5Cn/Gz9JqIxpw+tZaajsrtZrsoEwenZEND1Ya6AY
rnVCjCFdTmSVG9EnzGxFT40DOw0yIhEAw5WqfBzjwgNSfz+p44Bnb3jUHsJt38gw
analyst@8ff24c0cf742:~$ cat README.txt  
Hello,
All of your data has been encrypted. To recover your data, you will need to solve a cipher. To get started look for a hidden file in the caesar subdirectory.
