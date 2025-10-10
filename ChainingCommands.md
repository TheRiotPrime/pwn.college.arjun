# Linux Luminarium- Practising Piping

## My solve
### Challenge 1:
  **Flag**  pwn.college{8K9YFpo7eOWwWSsG3GrpNb9KWau.QX1UDO0wyM0AzNzEzW}
 To use the ; to chain commands and run two programs one after the other by just writing a single command.
 ``` 
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{8K9YFpo7eOWwWSsG3GrpNb9KWau.QX1UDO0wyM0AzNzEzW}
hacker@chaining~chaining-with-semicolons:~$ 
```
## What I learned
To use ; commmand.

### Challenge 2:
  **Flag** pwn.college{4qP5U--gp_HElFU8dfVMROofnqe.0lM0MDOxwyM0AzNzEzW}
 Here we are using the && argument to chain commands. The second command only takes place if the first one is executed successfully.
 ``` 
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second 
Nice chaining! Flag: pwn.college{4qP5U--gp_HElFU8dfVMROofnqe.0lM0MDOxwyM0AzNzEzW}
hacker@chaining~building-on-success:~$ 
```
## What I learned
To use the && to chain commands.

### Challenge 3:
  **Flag**  pwn.college{YC5hfJ-obj-vVUcfCefW058EYim.01M0MDOxwyM0AzNzEzW}
  Here we are using the || argument to run the second command in case the first failed.
 ``` 
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second 
Nice chaining! Flag: pwn.college{YC5hfJ-obj-vVUcfCefW058EYim.01M0MDOxwyM0AzNzEzW}
hacker@chaining~handling-failure:~$ 
```
## What I learned
To use the || in chaining commands.

### Challenge 4:
  **Flag** pwn.college{o2uCJMeZ2DJ9zhAk9g-6OPhEvUj.QXxcDO0wyM0AzNzEzW}
Here we are writing a shell script. We are redirecting the output from two programs pwn and college into the shell script x and we are running that file to get the flag.
``` 
hacker@chaining~your-first-shell-script:~$ echo "/challenge/pwn; /challenge/college" > x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{o2uCJMeZ2DJ9zhAk9g-6OPhEvUj.QXxcDO0wyM0AzNzEzW}
hacker@chaining~your-first-shell-script:~$ 
```
## What I learned
To write a shell script

### Challenge 5:
  **Flag**  pwn.college{IM9D6Tp8GSsaStUOuPNxq65kMoS.QX4ETO0wyM0AzNzEzW}
 To use the ; to chain two commands and put them into a shell script x which is then piped into the solve program to get the flag.
 ``` 
hacker@chaining~redirecting-script-output:~$ echo "/challenge/pwn ; /challenge/college" > x.sh 
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{IM9D6Tp8GSsaStUOuPNxq65kMoS.QX4ETO0wyM0AzNzEzW}
hacker@chaining~redirecting-script-output:~$ 

```
## What I learned
To use the shell script to pipe the output of more than one program into the input of another.

### Challenge 6:
  **Flag** pwn.college{8wJ5oF_mcyb1I9-jZj7sAw9wCSb.QX0cjM1wyM0AzNzEzW}
  Here we are making this shell script executable using file permissions by giving permission to user using chmod. If we do so we can run this shell script without using bash and just by running it as any other program.
 ``` 
hacker@chaining~executable-shell-scripts:~$ echo "/challenge/solve" > x.sh
hacker@chaining~executable-shell-scripts:~$ chmod ugo+x x.sh
hacker@chaining~executable-shell-scripts:~$ ls -l
total 48
-rw-r--r-- 1 hacker hacker   4 Sep 28 16:44 COLLEGE
drwxr-xr-x 1 hacker hacker   0 Sep 29 10:14 Desktop
-rw-r--r-- 1 hacker hacker   8 Sep 28 11:12 PWN
-rw-r--r-- 1 root   hacker  77 Sep 28 17:27 echo
-rw-r--r-- 1 hacker hacker  77 Sep 28 17:30 file
-rw-r--r-- 1 root   hacker  60 Sep 23 09:26 h
-rw-r--r-- 1 hacker hacker 829 Sep 28 16:51 instructions
-rw-r--r-- 1 hacker hacker  95 Sep 28 16:51 myflag
lrwxrwxrwx 1 hacker hacker   5 Sep 26 19:44 not-the-flag -> /flag
-rw-r--r-- 1 root   hacker  77 Sep 28 17:27 pwn
-rw-r--r-- 1 root   hacker  60 Sep 23 10:56 r
-rw-r--r-- 1 hacker hacker   0 Sep 28 09:56 stdout
-rw-r--r-- 1 hacker hacker 437 Sep 28 16:49 the-flag
-rw-r--r-- 1 hacker hacker   0 Oct  9 20:37 x
-rwxr-xr-x 1 hacker hacker  17 Oct 10 04:25 x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{8wJ5oF_mcyb1I9-jZj7sAw9wCSb.QX0cjM1wyM0AzNzEzW}
hacker@chaining~executable-shell-scripts:~$ 
```
## What I learned
To make shell scripts executable.

### Challenge 7:
  **Flag**  pwn.college{U9PSJAziJHvoI6yWoMQiBW9rKaC.0VOzMDOxwyM0AzNzEzW}
  Here we are using shebangs which acts as an interpreter and it gives the path to the interpreter for the next lines of the program.
 ``` 
hacker@chaining~understanding-shebangs:~$ echo '#!/bin/bash ; echo "hack the planet"' > /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod ugo+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Your script did not give the expected output.
Expected: hack the planet
Got: 
hacker@chaining~understanding-shebangs:~$ echo '#!/bin/bash /n  echo "hack the planet"' > /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod ugo+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Your script did not give the expected output.
Expected: hack the planet
Got: 
hacker@chaining~understanding-shebangs:~$ echo '#!/bin/bash \n  echo "hack the planet"' > /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod ugo+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Your script did not give the expected output.
Expected: hack the planet
Got: 
hacker@chaining~understanding-shebangs:~$ echo '#!/bin/bash \necho "hack the planet"' > /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Your script did not give the expected output.
Expected: hack the planet
Got: 
hacker@chaining~understanding-shebangs:~$ echo"#!/bin/bash" && echo "hack the planet" > /home/hacker/solve.sh
bash: !/bin/bash: event not found
hacker@chaining~understanding-shebangs:~$ echo -e '#!/bin/bash\necho "hack the planet"' > /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod ugo+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{U9PSJAziJHvoI6yWoMQiBW9rKaC.0VOzMDOxwyM0AzNzEzW}

hacker@chaining~understanding-shebangs:~$ 
```
## What I learned
To write shebangs.

### Challenge 8:
  **Flag** pwn.college{g7f7dGb_tDp6R_2bTaWht0soFh-.0VNzMDOxwyM0AzNzEzW}
Here we are giving two arguments to a shell script and we have written the script so as to reverse the output giving the second argument back and then the first.
``` 
hacker@chaining~scripting-with-arguments:~$ echo -e '#!/bin/bash\necho "$2 $1"' > /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ chmod a+x /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ /home/hacker/solve.sh pwn college
college pwn
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{g7f7dGb_tDp6R_2bTaWht0soFh-.0VNzMDOxwyM0AzNzEzW}
hacker@chaining~scripting-with-arguments:~$ 
```
## What I learned
To write the shell scripts with arguments.

### Challenge 9:
  **Flag**  pwn.college{gD9BV8lle8Ba_p0h5tBgCx5Dm5S.0lNzMDOxwyM0AzNzEzW}
 We are creating a shell script with an if conditon to check if the attribute of the command is pwn and if so replace it by college.
 ``` 
hacker@chaining~scripting-with-conditionals:~$ echo -e '#!/bin/bash\nif [ "$1" = "pwn" ]; then\n  echo "college"\nfi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{gD9BV8lle8Ba_p0h5tBgCx5Dm5S.0lNzMDOxwyM0AzNzEzW}
hacker@chaining~scripting-with-conditionals:~$

```
## What I learned
To use if condition in Linux.

### Challenge 10:
  **Flag** pwn.college{wvG-a88o3k1eA7q-ulloYQKRu66.01NzMDOxwyM0AzNzEzW}
 Here we are using the if condition along with an else condition in the shell script. If the attribute is pwn, then college gets printed else nope gets printed.
 ``` 
hacker@chaining~scripting-with-default-cases:~$ echo -e '#!/bin/bash\nif [ "$1" = "pwn" ]; then\n  echo "college"\n else \n echo "nope" \nfi' > /
home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{wvG-a88o3k1eA7q-ulloYQKRu66.01NzMDOxwyM0AzNzEzW}
hacker@chaining~scripting-with-default-cases:~$ 
```
## What I learned
To use if else conditions.

### Challenge 11:
  **Flag**  pwn.college{MjwXsiIHHXAAeJze-mPNWafi-YY.0FOzMDOxwyM0AzNzEzW}
  Here we are using the else if ladder to check every single condition specified and to do the else case in the end in case nothing before satisfies.
 ``` 
hacker@chaining~scripting-with-multiple-conditions:~$ echo -e '#!/bin/bash\nif [ "$1" = "hack" ]; then\n  echo "planet"\n elif [ "$1="pwn" ]; then\n echo "college"\n elif [ "$1="learn" ]; then\n echo "linux" \n else echo "unknown" \nfi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Test failed for input 'hack'
Expected: 'the planet'
Got: 'planet'
hacker@chaining~scripting-with-multiple-conditions:~$ echo -e '#!/bin/bash\nif [ "$1" = "hack" ]; then\n  echo "the planet"\n elif [ "$1="pwn" ];
 then\n echo "college"\n elif [ "$1="learn" ]; then\n echo "linux" \n else echo "unknown" \nfi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Test failed for input 'pwn'
Expected: 'college'
Got: 'linux'
hacker@chaining~scripting-with-multiple-conditions:~$ echo -e '#!/bin/bash\nif [ "$1" = "hack" ]; then\n  echo "the planet"\n elif [ "$1="pwn" ]; then\n echo "college" \n elif [ "$1="learn" ]; then\n echo "linux" \n else echo "unknown" \nfi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Test failed for input 'pwn'
Expected: 'college'
Got: 'linux'
hacker@chaining~scripting-with-multiple-conditions:~$ echo -e '#!/bin/bash\nif [ "$1" = "hack" ]; then\n  echo "the planet"\nelif [ "$1" = "pwn" ]; then\n  echo "college"\nelif [ "$1" = "learn" ]; then\n  echo "linux"\nelse\n  echo "unknown"\nfi' > /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{MjwXsiIHHXAAeJze-mPNWafi-YY.0FOzMDOxwyM0AzNzEzW}
hacker@chaining~scripting-with-multiple-conditions:~$ 
```
## What I learned
To use the else if ladder.

### Challenge 12:
  **Flag** pwn.college{AFmcIB0Yg_pYzfNofHy6DnX4bx-.0lMwgDOxwyM0AzNzEzW}
Here we are running the run program to get the password and then we pipe the password into the input of the run program.
``` 
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ ls
COLLEGE  Desktop  PWN  echo  file  h  instructions  myflag  not-the-flag  pwn  r  solve.sh  stdout  the-flag  x  x.sh
hacker@chaining~reading-shell-scripts:~$ echo "hack the PLANET" > /challenge/run
bash: /challenge/run: Permission denied
hacker@chaining~reading-shell-scripts:~$ echo "hack the PLANET" | /challenge/run
CORRECT! Your flag:
pwn.college{AFmcIB0Yg_pYzfNofHy6DnX4bx-.0lMwgDOxwyM0AzNzEzW}
hacker@chaining~reading-shell-scripts:~$ 
```
## What I learned
To read a system shell script.

## References
None
