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
