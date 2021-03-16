# Linux Fundamentals Part 1

## Task 1 - Intro

This room covers Intro to Linux, Executing Commands and viewing 'man' pages as well as basic file operators.

I need to deploy the machine to get started.

## Task 2 - Methodology

Looks like they want to use the waterfall life cycle/method. Each future task is going to be fed off of from a previous task.

## Task 3 - Section 2: Running Commands - Basic Command Execuition

I'm logged into the server. Everything can be done over SSH.
I'm introduced to the 'echo' command. I am to type 'echo hello' and press Enter. I see the input is echoed back to me, cool!

## Task 4 - Section 2: Running Commands - Manual Pages and Flags

Most commnds have options that are called flags. You can add a flag/option to a command to have it do something specific. You can view these options/flags with the 'man' command.
To view the 'man' or 'manual' page of a command, simply type 'man <command>' replacing <command> with whichever command you wish to view the manual page for.

Ex: man echo

![image](https://user-images.githubusercontent.com/36644707/111370178-4b225d80-866e-11eb-9572-603f04db5c14.png)
</br>
![image](https://user-images.githubusercontent.com/36644707/111370201-52e20200-866e-11eb-9231-2810f607b1cd.png)
</br>
</br>
There is a ton of inormation about the flags here. -n is used to remove the newline. 

SOME commands, not all, can also just use the -h flag to get a list of flags and other useful information
about the command without actually viewing the man page, <command> -h.

You can output hello without a newline with the echo -n hello

## Task 5 - Section 3: Basic File Operations - ls

ls is a command that lists info about every file and directory within the current director. Using the -a flag with the ls command will list all files/directoried including ones
that start with "."

ls with the -l flag outputs in a "long list format"

## Task 6 - Section 3: Basic File Operations - cat

"cat" is shor for concatenate. it outputs the contents of the files to the console. If you had a file named "a.txt" and ran "cat a.txt", this would output all the contents of
a.txt to the current console.

cat supports the --help flag. This means that you can see useful flags without using the man page.

The -n flag with the cat command numbers ALL output lines.

## Task 7 - Section 3: Basic File Operations - touch

touch is a simple command to creat files. Running the "touch b.txt" will create a .txt file named b

## Task 8 - Section 3: Basic File Operations - Running A Binary

Sometimes you will want to run download or user created programs. You can do this by providing the full path to the binary (program). 

Like so,

![image](https://user-images.githubusercontent.com/36644707/111371630-11eaed00-8670-11eb-887a-5b8b55cd8ef7.png)
</br>

** A binary is just executable code, like a windoes .exe file.

Each time you want to run a binary, you dont have to provide the FULL path. You can just use its RELATIVE path.

Relative paths are:

.   which means "current directory"    ./hello means you want to run the "hello" binary in your current working direcory.
..  which means "direcory befor/above current direcotory"  ../hello will run the "hello" binary in the directory above the current working directory.
~   which means "the user's home directory"     ~/hello means it will run the "hello" binary in the user's home directory.

## Task 9 - Binary - Shiba1

To complete this challenge, create a file called 'noot.txt'

touch noot.txt

Now we need to run the binary shiba1. We can use ./shiba1 for the relative path for the binary.

![image](https://user-images.githubusercontent.com/36644707/111372364-eddbdb80-8670-11eb-9c98-e57b04c97228.png)
</br></br>

pinguftw is the password for shiba2

## Task 10 - su

Now that we have shiba2 password. We can cover su. su allows us to switch user accounts without actually logging out and back into another account. We can switch to shiba2 by
typing su shiba2 in the console.

We are then met with a password prompt, shiba2's password was discovered in the previous task - pinguftw

![image](https://user-images.githubusercontent.com/36644707/111372594-372c2b00-8671-11eb-84a1-4ef82809694b.png)
</br>

Once we put this pw in for shiba2, we are now logged in as shiba2

![image](https://user-images.githubusercontent.com/36644707/111372648-4d39eb80-8671-11eb-900e-71d1db51e8dd.png)
</br>

## Task 11 - Linux Fundamentals 2

Now that we have some beginner knowledge using Linux, we should move onto Linux Fundamentals 2 room. We need to terminate the machine and move onto the next room
