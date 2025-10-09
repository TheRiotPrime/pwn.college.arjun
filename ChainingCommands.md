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
## References
None
