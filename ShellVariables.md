# Linux Luminarium- Shell Variables

## My solve
### Challenge 1:
  **Flag**  pwn.college{QiqzKWu3eKnLXf7_8qogLkIDGRl.QX3UTN0wyM0AzNzEzW}
 To use the echo command to print out variables
 ``` 
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{QiqzKWu3eKnLXf7_8qogLkIDGRl.QX3UTN0wyM0AzNzEzW}
hacker@variables~printing-variables:~$ 

```
## What I learned
To use $ symbol with filenames to print variables with echo.

### Challenge 2:
  **Flag** pwn.college{A5HXrSZ8bXMKV4YhGFpdx3ebG3Z.QX5UTN0wyM0AzNzEzW}
 Here we are using the = operator to assign value COLLEGE into variable PWN
 ``` 
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{A5HXrSZ8bXMKV4YhGFpdx3ebG3Z.QX5UTN0wyM0AzNzEzW}
hacker@variables~setting-variables:~$ 
```
## What I learned
To use the = operator to assign values to variable.

### Challenge 3:
  **Flag**  pwn.college{wWJx9B4f9_WRTBzs1RO_Hc_FYsS.QXwYTN0wyM0AzNzEzW}
  Here we are quotes while assigning value that has white space to a variable.
 ``` 
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{wWJx9B4f9_WRTBzs1RO_Hc_FYsS.QXwYTN0wyM0AzNzEzW}
hacker@variables~multi-word-variables:~$ 
```
## What I learned
To use quoting while assigning values to variables.

### Challenge 4:
  **Flag** pwn.college{M9GWsJDVa04mcSmWRYDSk4FGBu4.QXyYTN0wyM0AzNzEzW}
Here we are using the export to export the PWN variable which has the value COLLEGE. This is then called from a new shell environment that has been made using the sh command.We have aslo set the value of COLLEGE variable as PWN but it's not exported.
 ``` 
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ sh
sh-5.2$ /challenge/run $PWN
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{M9GWsJDVa04mcSmWRYDSk4FGBu4.QXyYTN0wyM0AzNzEzW}
sh-5.2$ 
```
## What I learned
About exporting variables and the sh command to create a child shell environment.

### Challenge 5:
  **Flag**  pwn.college{kSQzs9eslO1hmlT6rqUGEnmeyPg.QX4UTN0wyM0AzNzEzW}
  
Here we are using the env command to output all exported variables in the shell.
 ``` 
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=8adb4d354781f30048de5ec0924e9aa1e96ec42c249e93ed31e768eb742fce54
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{kSQzs9eslO1hmlT6rqUGEnmeyPg.QX4UTN0wyM0AzNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
hacker@variables~printing-exported-variables:~$ 
```
## What I learned
To use env command.

### Challenge 6:
  **Flag**  pwn.college{Idy7ntnFWX3t6XomxBnFpEHo4zz.QX1cDN1wyM0AzNzEzW}
Here we are using the $() command to read the output of a file directly into a variable.
 ``` 
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ cat PWN
COLLEGE
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{Idy7ntnFWX3t6XomxBnFpEHo4zz.QX1cDN1wyM0AzNzEzW}
hacker@variables~storing-command-output:~$ 
```
## What I learned
To use the $() command.

### Challenge 7:
  **Flag**  pwn.college{ohJkX8XHUla4mn26hQktQapXpR7.QX4cTN0wyM0AzNzEzW}
Here we are using the read command to get input from the user. We are assigning the value COLLEGE into PWN variable.
 ``` 
hacker@variables~reading-input:~$ read -p "INPUT: " PWN
INPUT: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{ohJkX8XHUla4mn26hQktQapXpR7.QX4cTN0wyM0AzNzEzW}
hacker@variables~reading-input:~$ 
```
## What I learned
The use of read command in Linux.

### Challenge 8:
  **Flag**  pwn.college{stMmoGhaGww5Zk8E9HRNDmQuHJ6.QXwIDO0wyM0AzNzEzW}
Using the read command to directly read the value into a variable directly from the output of a program.
 ``` 
hacker@variables~reading-files:~$ read PWN < $(/challenge/read_me)
You appear to be invoking a subshell. This could be, for example, because you 
are doing something like `PWN=$(echo COLLEGE)`. Instead, you must use `read` to 
set the PWN variable.
bash: $(/challenge/read_me): ambiguous redirect
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{stMmoGhaGww5Zk8E9HRNDmQuHJ6.QXwIDO0wyM0AzNzEzW}
hacker@variables~reading-files:~$ 
```
## What I learned
Using the read command directly to read in the output of a program without a seperate program.

## References
None
