## Linux Fundamentals Part 2

## Task 1 - Intro

This room covers Linux Operators and Advanced File Operators.
We need to deploy the machine and SSH into the room as explained. The username is shiba2 and the pw is pinguftw

***This is not a browser based machine, we need to SSH into it.***

We'll learn how to do this in the following tasks.

## Task 2 - SSH Intro

SSH (secure shell) is used to securely access a machine remotely. SSH allows us to run commands on the remote machine.
SSH is CLI (command line interface) oriented, no flashy GUI (graphical user interface) here. This is how most servers run with CLI.

This section will focus on SSH with Windows program, PuTTY. 

## Task 3 - PuTTY and SSH

Find the most recent release of PuTTY, <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">here</a>.

Insert the IP address of the deployed machine in the "Host Name (or IP address) field.
shiba2@IPaddress and leave the port on 22 since SSH uses port 22.

Click 'yes' on the prompt. Enter 'pinguftw' as the password.

## Task 4 -Section 4: Linux Operators &&

&& means "and". This means you can execute a second command after the first one has executed ***successfully***.

ls && echo hello will work fine since the first command is valid.
lnasdifnwefneknasdiopfnse && echo hello will not work because the gibberish command is not valid, thus the second command will not work.

## Task 5 - Section 4: Linux Operators &

& has nothing to do with 'and' at all. It allows you to run a second command while the first one is still completing.

## Task 6 - Section 4: Linux Operators $

The $ is a special operator used to denote environment variables. These variables are set by the computer but you can set them up as well. These are used to affect different processes and how they work. If you edit these variables you can change how certain processes work on your computer. For example, your current user is always stored in an environment variable called $USER. You can view these variables with the echo command, "echo $USER"

![image](https://user-images.githubusercontent.com/36644707/111397461-bf252b80-8697-11eb-8214-3cbd43356b8b.png)
</br></br>

This means environment variables can be used as input for other commands as well, for example say I wanted to create a file which is the name of our current user, I could do "touch $USER"

![image](https://user-images.githubusercontent.com/36644707/111397608-175c2d80-8698-11eb-8976-570207d036f4.png)
</br></br>

I can use "echo hi >> $USER" and this will echo 'hi' and append it INTO the $USER file I just created.

Env. variables can be set pretty easily as well, just run "export <varname>=<value>" will set that as an environment variable.
  
I can set nootnoot equal to 1111 by running "export nootnoot=1111"

I can use "echo $HOME" to view the value of the home environment variable

![image](https://user-images.githubusercontent.com/36644707/111397902-bf71f680-8698-11eb-88fa-79ea54aae633.png)
</br></br>

## Task 7 - Section 4: Linux Operators |

The pipe | is unique because while operators like >> allows you to store the output of a command, the | operator allows you to take the output of one command and use it as the input for a second command.

I can use "cat" to get the output of a file and pipe that into a "grep" command to search for a specific string.

![image](https://user-images.githubusercontent.com/36644707/111398242-7cfce980-8699-11eb-87b5-254630511ff2.png)
</br></br>

**Not all commands support the pipe command.** Some that do support it require you to use - instead of input. For example "cat -" So always check to see if the command does support the | pipe command.

## Task 8 - Section 4: Linux Operators ;

The ; operator works much liek the && command but it does not require the first command to execute successfully. This means that you can run a gibberish command like "laksdofnenoanefon ; ls" and the fist command will fail because its malarchy, but the second command "ls" will still run.

## Task 9 - Section 4: Linux Operators >

The > operator is for output redirection. You can redirect the output of any command to a file. If you ran "echo hello > file" then instead of outputting hello to the console it would save that output to a file called file.

**If you use this command on a file that already exists, it would completely erase the contents of the original file and replace it with the output from your run command.**

![image](https://user-images.githubusercontent.com/36644707/111398652-42e01780-869a-11eb-8257-f7572bc9a2f2.png)
</br></br>

## Task 10 - Section 4: Linux Operators >>

The >> command does the same as > but >> appends to the end of the file instead of erasing it.

![image](https://user-images.githubusercontent.com/36644707/111398822-820e6880-869a-11eb-8a64-b7939c785b90.png)
</br></br>

## Task 11 - Binary shiba2

This challenge requires us to set an environment variable to "test1234" and set it equal to $USER, then run shiba2 binary.

We run "ls -al" to list the contents of the directory in long list form to include . and .. 
We can see the binary shiba2 at the bottom and we seet that its a file and not a directory.

![image](https://user-images.githubusercontent.com/36644707/111399700-42e11700-869c-11eb-8698-32ce6148efc5.png)
</br></br>

I set the value of "test1234" equal to the $USER environment varibale and then run the binary shiba2 after. We then get the password for shiba3, ***happynootnoises***

![image](https://user-images.githubusercontent.com/36644707/111399770-699f4d80-869c-11eb-9388-8f7f224462a7.png)
</br></br>

## Task 12 - Section 5: Advanced File Operations: Intro

Files have  alot of complexity to them, much like Windows. Different parameters have to be modified to allow certain users to read
to file, write to file and to execute them. This section will cover modifying those paramenters.

## Task 13: Section 5: Advanced File Operatros: A bit of background

Remember that "ls" has differnt flags that allow to view information about differnt file types. We want to focus on the attributes associated with the file. The attributes are in order, left to right, the file permissions, the currernt owner of the file and the group that the file belongs to.

![image](https://user-images.githubusercontent.com/36644707/111400087-fa762900-869c-11eb-9e0a-6eb0c7ed5fe8.png)
</br></br>

## Task 14: Section 5: Advance File Operations: chown

ls shows us our username twice for current owner and group. We can edit the permissions with the "chown" command. chown stands for change ownership. You can change the user and group for any file with chown. The syntax is "chown user:group file" You can only chown if you are **ABOVE** that user, meaning its best to just run chown as root user.

It's good to note that you dont have to change ownership of both user and group, you can just "chown user file" or "chown group file"

I can change the owner of a file to paradox by running "chown paradox file"
I can change the owner and the group of file to paradox with "chown paradox:paradox file"
The flag to allow me to operate on **every** file in the directory at once is -R for recursive. 

## Task 15 - Section 5: Advanced File Operations: chmod

chmod - change file mode bits (change read, write, execute permissions for a file/directory)

The syntax of this command is "chmod <permissions> <file>"
  
The permissions are set with 3 digit numbers. The numbers are sumations of the following digits: 1 execute, 2 write and 4 read.

So, if you want to read (4) and execute (1), the final digit would be 5.
If you want to execute (1) and write (2), the final digit would be 3.
If you want to read (4), write (2), and execute (1), the final digit would be 7.

You get the point.

"chmod 341 file" would change the permissions to be executed and written to by user that owns the file, the file can be read by the group that owns the file and the file can be executed by everyone

![image](https://user-images.githubusercontent.com/36644707/111402632-e84ab980-86a1-11eb-9e41-b37c23fac66a.png)
</br></br>

The permissions that llow the user to read the file, the group can read and write the file and no one else can read, write or execute the fiel is:   460

The permissions that the user can read, write, and execute the file, the group can read, write, and execute the file, and everyone else can read, write, and execute the file is:    777.

## Task 16 - Advanced File Operations: rm

rm means remove and that's exactly what it does. It can completely destroy your whole Linux system.

The -r flag deletes every file in a directory.
The -f flag suppresses all warning prompts.

## Task 17 - Section 5: Advanced File Operations: mv

To move files from one place to another is ***mv***. The syntax is "mv <file> <destination>". If you wanted to move a file to the home directory your would type "mv file ~"
  
You can also use ***mv*** to change the name of a file, "mv file ~/gfhds" will rename file to gfhds

## Task 18 - Linux Fundamentals 3

Now that we have some intermediate knowledge to using Linux, we can finish the Linux series with Linux Fundamentals 3 room.
