# Linux Luminarium- Data Manipulation 
The challenge helps to get familiar with useful and important Linux commands.

## My solve
### Challenge 1:
  **Flag**  pwn.college{MDptfvqKxVVyb0gKDk8bxk2_TPY.01MxEzNxwyM0AzNzEzW}
  Here we are running a tr command along with piping to change thew case of the flag. The tr command translates and replaces certain characters wiuth the specific ones we need. The first character mentioned as the argument is replaced by the second charatcer argument.
 ``` 
hacker@data~translating-characters:~$ /challenge/run | tr abcdefghijklmnopqrstuvwxyz ABCDEFGHIJKLMNOPQRSTUVWXYZ
YOUR CASE-SWAPPED FLAG:
PWN.COLLEGE{MDPTFVQKXVVYB0GKDK8BXK2_TPY.01MXEZNXWYM0AZNZEZW}

hacker@data~translating-characters:~$ /challenge/run | tr abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz
yOUR CASE-SWAPPED FLAG:
pwn.college{MDptfvqKxVVyb0gKDk8bxk2_TPY.01MxEzNxwyM0AzNzEzW}

hacker@data~translating-characters:~$
```
## What I learned
To use the tr command in Linux

### Challenge 2:
  **Flag**  pwn.college{4z2smCBNYRAtFPILCK6G4XK7-Ei.0FNxEzNxwyM0AzNzEzW}
  Here we are using the tr command with the -d argument to delete specific characters from the flag. 
 ``` 
hacker@data~deleting-characters:~$ /challenge/run
Your character-stuffed flag:
p^%wn^.^c^o^ll^%e%g^e^{4%z^%2%sm^CB^%N^%YR^A^t^%F^%P^%I^%LC%K^6%G%4^%X^%K^7^-^E%i^.%0^%F^%N^x%E%z%N^%x^w^y%M^%0%AzNz^%E^z^%W}^
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{4z2smCBNYRAtFPILCK6G4XK7-Ei.0FNxEzNxwyM0AzNzEzW}
hacker@data~deleting-characters:~$ 
```
## What I learned
Learned to delete characters with tr command.

### Challenge 3:
  **Flag**  pwn.college{QuzMYyaevhVYhgqUL9fHVNChZ5r.0VNxEzNxwyM0AzNzEzW}
 Here we are using the \n to create a new line. we use the tr tag to remove all newlines in the flag so as to obtain it
 ``` 
hacker@data~deleting-newlines:~$ /challenge/run | tr -d "\n"
Your line-split flag: pwn.college{QuzMYyaevhVYhgqUL9fHVNChZ5r.0VNxEzNxwyM0AzNzEzW}hacker@data~deleting-newlines:~$
```
## What I learned
To use tr tag to add a new line in between texts.

### Challenge 4:
  **Flag**  pwn.college{Itgn-YkVwW_mKwfhbq53SAdJwXC.0lNxEzNxwyM0AzNzEzW}
 Here we are using the head command to extract the first few required number of lines from the output of /challenge/pwn program and then we are piping it into another program /chaallenge/college. Here we use the -n 7 attribute to limit the number of lines.
 ``` 
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge college
bash: /challenge: Is a directory
head: write error: Broken pipe
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challeng/college
bash: /challeng/college: No such file or directory
head: write error: Broken pipe
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{Itgn-YkVwW_mKwfhbq53SAdJwXC.0lNxEzNxwyM0AzNzEzW}
hacker@data~extracting-the-first-lines-with-head:~$ 
```
## What I learned
To use head command.

## References 
pwn.college video
https://www.youtube.com/watch?v=m55AtwjBXpE&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC
