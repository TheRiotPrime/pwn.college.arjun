# Linux Luminarium- Pondering PATH

## My solve
### Challenge 1:
  **Flag**  pwn.college{UQEDsL8K30PCCv0RM8hP2Fp49Sz.QX2cDM1wyM0AzNzEzW}
  Here we are changing the PATH to nil so that the run program won't be able to access the required files so as to delete the flag.
 ``` 
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ ls
bash: ls: No such file or directory
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{UQEDsL8K30PCCv0RM8hP2Fp49Sz.QX2cDM1wyM0AzNzEzW}
hacker@path~the-path-variable:~$ 
```
## What I learned
To use the PATH in Linux.

### Challenge 2:
  **Flag**  pwn.college{89uRu7-NdKrGP_2zUpVO01JFoLu.QX1cjM1wyM0AzNzEzW}
  Here we are using a  particular path which contains the required files to run the program properly.
 ``` 
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run 
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{89uRu7-NdKrGP_2zUpVO01JFoLu.QX1cjM1wyM0AzNzEzW}
hacker@path~setting-path:~$ 
```
## What I learned
Learned to use PATH to direct a program.

### Challenge 3:
  **Flag**  pwn.college{UjtRBQqel7fP9O9U9sevgPLcjRq.01NzEzNxwyM0AzNzEzW}
 Here we are using the which command to find the path of a particular command and then we are using that to run the program.
 ``` 
hacker@path~finding-commands:~$ which win
/challenge/paths/24803/win
hacker@path~finding-commands:~$ cat /challenge/paths/24803/ flag
cat: /challenge/paths/24803/: Is a directory
cat: flag: No such file or directory
hacker@path~finding-commands:~$ cat /challenge/paths/24803/win flag
#!/bin/bash

/bin/fold -s <<< "Search for the flag in the same directory in which I am located!"
cat: flag: No such file or directory
hacker@path~finding-commands:~$ cat /challenge/paths/24803/flag
pwn.college{UjtRBQqel7fP9O9U9sevgPLcjRq.01NzEzNxwyM0AzNzEzW}
hacker@path~finding-commands:~$ 
```
## What I learned
To use which command.

### Challenge 4:
  **Flag**  pwn.college{IA5Gt65AnobKjlHqvZmsPDqhVGJ.QX2cjM1wyM0AzNzEzW}
 Here we are using the win command to create a new command so as to run the required program.
 ``` 
hacker@path~adding-commands:/challenge$ mkdir ~/mybins
hacker@path~adding-commands:/challenge$ echo 'cat /flag' > ~/mybins/win
hacker@path~adding-commands:/challenge$ chmod +x ~/mybins/win
hacker@path~adding-commands:/challenge$ export PATH=~/mybins:$PATH
hacker@path~adding-commands:/challenge$ /challenge/run
Invoking 'win'....
pwn.college{IA5Gt65AnobKjlHqvZmsPDqhVGJ.QX2cjM1wyM0AzNzEzW}
hacker@path~adding-commands:/challenge$ 
```
## What I learned
To use win command.

### Challenge 5:
  **Flag** pwn.college{ksUpDcqj22MVfDJ40zr-bqzMjT0.QX3cjM1wyM0AzNzEzW}
Here we are creating a command in the required path and then running our program.
 ``` 
hacker@path~hijacking-commands:~$ mkdir ~/fun
hacker@path~hijacking-commands:~$ echo 'cat /flag' > ~/fun/rm
hacker@path~hijacking-commands:~$ chmod +x ~/fun/rm
hacker@path~hijacking-commands:~$ export PATH=~/fun:$PATH
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/fun/rm. Executing!
pwn.college{ksUpDcqj22MVfDJ40zr-bqzMjT0.QX3cjM1wyM0AzNzEzW}
hacker@path~hijacking-commands:~$ 
```
## What I learned
To create a new command.

## References
None
## References 
None
