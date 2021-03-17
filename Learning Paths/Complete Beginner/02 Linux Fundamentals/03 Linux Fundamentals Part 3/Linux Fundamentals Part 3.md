# Linux Fundamentas Part 3

## Task 1 - Intro

This room will cover vairous Linux concepts and built-in tools. Topics include: Admanced File Operators, Users & Groups and Introduction to Shell Scripting.

We need to deploy the machine ans SSH into the room using the following username and password:

shiba3
happynootnoises

## Task 2 - Section 5: Advanced File Operations - cp

In order to duplicate a file you use the ***cp*** command. The syntax for this command is "cp <file> <destination>".
  
![image](https://user-images.githubusercontent.com/36644707/111407093-bccbcd00-86a9-11eb-9dfa-66d8e094570f.png)
</br></br>
  
## Task 3 - Section 5: Advanced File Operations - cd && mkdir

In Linux you can use the ***cd*** command to change directories. The syntax is "cd <directory>". Relative Paths are supported as well as absolute paths. You can use cd .. to change to the directory directly above the present working directory.
  
![image](https://user-images.githubusercontent.com/36644707/111406818-534bbe80-86a9-11eb-8c8d-5a791d7435c3.png)
</br></br>
  
In order to make a new directory to store files in, use the ***mkdir*** command. The syntax of mkdir is "mkdir <directory name>"

![image](https://user-images.githubusercontent.com/36644707/111407759-90fd1700-86aa-11eb-9dce-121b0fa71d3a.png)
</br></br>

I can cd to my home directory using relative paths with:   cd ~
I can make a directory called text in /tmp using absolute paths using:  mkdir /tmp/test

## Task 4 - Section 5: Advanced File Operations - ln

Hard Linking with ***ln*** completely duplicates the file, then links the duplicated to the originial copy. Whatever is done to the duplicate is also done to the original. The syntax for hard linking is, "ln source destination"

![image](https://user-images.githubusercontent.com/36644707/111408378-9870f000-86ab-11eb-8cbe-041cc2145b53.png)
</br></br>

Symbolic linking (symlink) is just refrencing to another file. The syntax for symbolic linking is "ln -s <file> <destination>"
  
![image](https://user-images.githubusercontent.com/36644707/111408765-25b44480-86ac-11eb-8439-29b28eea14f6.png)
</br></br>

I would link /home/test/testfile to /tmp/test with the following command:  ln /home/test/testfile /tmp/test

## Task 5 - Section 5 - Advanced File Operations: find

You can use the ***find*** command to find files. It does this by listing ever fil ein the current directory.
This only lists files that you have access to, if you run the "find /" command, it would list every file on the OS, **but** only
list what your user account has access to.

You can use the -user argument to list every file owned by a specific user,"find dir -user"; you can use the -group argument to list every file owned by a specific group, "find dir -group".

**It is highly recommended to read the manual page for the find command. The command is invaluable when working with files.**

I can find files with specific permissions using the flag -perm.
I can find all the files in the /home command with: find /home.
I can find all the files owned by paradox on the whole system with: find / -user paradox

## Task 6 - Section 5: Advanced File Operations - grep

The ***grep*** command allows you to search for data within data. The syntax is "grep <string> <file>". You can search multiple files at athe same time with "grep <string> <file> <file2>".
  
Lets say you have a filename for a log but you don't know where it is on the system. Use the ***find*** command to list every file on the OS, and then ***grep*** to find the actual file.
"find /* | grep test1234"

![image](https://user-images.githubusercontent.com/36644707/111410798-c6f0ca00-86af-11eb-858d-9120c150593c.png)
</br></br>

Lets say you also have a ton of data, but you want to find a string and specifically which line its at within a file.
grep hello test -n will do this. You will search the test file for the string "hello" and output the line number.

![image](https://user-images.githubusercontent.com/36644707/111410888-f56ea500-86af-11eb-9ae6-5aaeb192a443.png)
</br></br>

The -n flag lists line numbers for every string found.
I can use "grep boop /tmp/aaaa" to search for the string boop in the file aaaa in the directory /tmp.

## Task 7 - Binary - Shiba3

We need to run the shiba4 binary but we don't know where the binary is, we have to search for it. The binary is going to check if there is a directory called "test" in our home directory and that there is a file called test1234 in that newly created directory.

I did this by running the "mkdir test && cd test && touch test1234" command. This makes a direcotry named test then changes into that directory and then creates a file named test1234.

I then ran "find /* | grep shiba4" to search the entire OS directory listing and locate a string that had shiba4 in it. I found the binary in the /opt/secret/ directory. 

![image](https://user-images.githubusercontent.com/36644707/111412027-03252a00-86b2-11eb-86bd-3f8fc9681964.png)
</br></br>

cd to that directory and run the binary.

![image](https://user-images.githubusercontent.com/36644707/111412052-11734600-86b2-11eb-80b4-14b15a2ca36e.png)
</br></br>

shiba4 password is "test1234"

## Task 8 - Section 6: Miscellaneous: Intro

THis next section is dedicated to all those miscellaneous command and concepts that are useful to know.

## Task 9 - Section 6: Miscellaneous: sudo

***whoami*** is a command to let you know your current user. "sudo <command>" allows you to run which ever <command> as root user aka administrator.

You can specify which user you want to ruan a command as with the -u flag, "sudo -u <user> <command>"
I can run the command "whoami" as jen using the following command, "sudo -u jen whoami"
You can use the -l flag to list your current sudo privileges, or list a user's privileges for the remote host.
  
## Task 10 - Section 6: Miscellaneous: Adding users and groups

You can add a user with "adduser" and a group with "addgroup". The snytax for both of these commands are "adduser <username>" and "addgroup <groupname>"
  
It's important to remember that only root has permsissions to add users and groups. 

You can add users to a group with the command "usermod -a -G <groups seperated by commas> <user>", this needs to be run as root. If you wanted to add the user noot to the group alpha, you would run "usermod -a -G alpha noot"
  
I would add the user test to the group test with "sudo usermod -a -G test test" command.

## Task 11 - Section 6: Miscellaneous: nano

nano is a terminal based text editor. "nano <file you want to write to>" is the command to bring this up.
  
## Task 12 - Section 6: Miscellaneous: Basic Shell Scripting

You can run commands, one after another, in Linux without using any special operators. This is done by storing the commands you want to run in a file with a .sh extension.

We'll create a bash script with the following and save as s.sh

![image](https://user-images.githubusercontent.com/36644707/111413444-a7a86b80-86b4-11eb-948a-dd9e2a193585.png)
</br></br>

We can then run this with bash using the following command, "bash s.sh"

![image](https://user-images.githubusercontent.com/36644707/111413474-b68f1e00-86b4-11eb-9200-d9281236ba0d.png)
</br></br>

You don't have to add the .sh file extension if you added a "shebang (#!)" and then the path to the shell we want used to run our commands, /bin/bash

![image](https://user-images.githubusercontent.com/36644707/111413606-efc78e00-86b4-11eb-938c-972924881663.png)
</br></br>

We then remove the .sh file extension and make the file executable with chmod.

![image](https://user-images.githubusercontent.com/36644707/111413677-17b6f180-86b5-11eb-9b25-781e59ba95a4.png)
</br></br>

Notice how the s is now green, and the file attributes are all rwx for user, group, and everyone.

The shebang, #!, must be at the beginning of the file.

## Task 13 - Section 6: Miscellaneous: Important Files and Directories

Everything on the linux file system extends from "/". The / is the same as C: in Windows. If you were to delete / you would delete every file on your system.

**/etc/passwd** - Stores user information; often used to see all the users on a system.
**/etc/shadow** - Has all the passwords of these users.
**/tmp** - Every file inside it gets deleted upon shutdown, used for temp files.
**/etc/sudoers** - Used to control the sudo permissions of every user on the system.
**/home** - The directory wherre all your download, documents etc. are; the equivalent on Windows is C:\Users\<username>
**/root** - The root user's home directory; the equivalent on Windows is C:\Users\Administrator
**/usr** - Where all your software is installed.
**/bin** - Used for system critical files; DO NOT DELETE
**/sbin** - Used for system critical files; DO NOT DELETE
**/var** - The Linux miscellaneous directory; a myriad of processes store data in /var
**$PATH** - Stores all the binaries you're able to run; same as $PATH on Windows

The ***which*** command shows you where an executable is in any of the $PATCH directories.

## Task 14 - Section 6: Miscellaneous: Installing packages (apt)

A package is essentially a program. Think of it like an .exe file on Windows. To install packages you need root permissions, as each package will likely modify some systme critical directories such as /usr.

The syntax to install packages is "apt install <package"

## Task 15 - Section 6: Miscellaneous: Processes

Each binary is a process while it's being run on Linux. A process is just another word for "a running program". A list of running USER CREATED processes can be viewed with the "ps" command.

If you want to view ALL SYSTEM processes you have to use the -ef flag, "ps -ef"

The second column that includes the 3 - 5 digit numbers are known as the Process ID's (PIDs) and they are how you interact with the processes. Majority of the time you will be wanting to stop these processes and that is completed with the "kill" command. They syntax is "kill <PID>"
  
Another way of interacting with processes is using the "top" command. Top shows you what processes are taking up the most of the systems resources.

**It is highly recommended to read the "top" man page. It included descriptions for what every value means, and how they affect your system.**

