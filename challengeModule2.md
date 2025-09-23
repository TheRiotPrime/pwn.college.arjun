# Linux Luminarium- Pondering Paths
The challenge helps to get familiar with Linux filesystems and how to access directories and use paths.

## My solve
### Challenge 1:
  **Flag**  pwn.college{c8G5G1Z6_CeHtc9Topv0_CcbUIa.QX4cTO0wyM0AzNzEzW}
  Here we are running a command to invoke a program in the root directory
 ``` 
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{c8G5G1Z6_CeHtc9Topv0_CcbUIa.QX4cTO0wyM0AzNzEzW}
hacker@paths~the-root:~$ 
```
### Challenge 2:
  **Flag**  pwn.college{YqgnKIaA35ebl0MxAsFrIDluuGn.QX1QTN0wyM0AzNzEzW}
  Here we are running a command to invoke a program in a folder in the root directory
 ``` 
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{YqgnKIaA35ebl0MxAsFrIDluuGn.QX1QTN0wyM0AzNzEzW}
hacker@paths~program-and-absolute-paths:~$ 
```
### Challenge 3:
  **Flag**  pwn.college{Ipl_5_qhTPgZAujaXMwQU82Zsnj.QX2QTN0wyM0AzNzEzW}
  Here we are running a command to invoke a program in a specified directory which is specified by compiler
 ``` 
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /sys directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /sys
hacker@paths~position-thy-self:/sys$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Ipl_5_qhTPgZAujaXMwQU82Zsnj.QX2QTN0wyM0AzNzEzW}
hacker@paths~position-thy-self:/sys$ 
```
### Challenge 4:
  **Flag**  pwn.college{4sWA0e8H-CZ5gru0s9nyR6bLUOB.QX3QTN0wyM0AzNzEzW}
  Here we are running a command to invoke a program in a specified directory which is specified by compiler
 ``` 
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /etc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /etc
hacker@paths~position-elsewhere:/etc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{4sWA0e8H-CZ5gru0s9nyR6bLUOB.QX3QTN0wyM0AzNzEzW}
hacker@paths~position-elsewhere:/etc$ 
```
### Challenge 5:
  **Flag**  pwn.college{kUjGeoKwSbMZc4-aI6D8zi5bt-I.QX4QTN0wyM0AzNzEzW}
  Here we are running a command to invoke a program in a specified directory which is specified by compiler
 ``` 
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /var directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /var
hacker@paths~position-yet-elsewhere:/var$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{kUjGeoKwSbMZc4-aI6D8zi5bt-I.QX4QTN0wyM0AzNzEzW}
hacker@paths~position-yet-elsewhere:/var$ 
```
### Challenge 6:
  **Flag**  pwn.college{cKmcjGLoAWEgSXjqA9-6YfQUL1Z.QX5QTN0wyM0AzNzEzW}
  Here we are running a command to invoke a program using relative paths instead of absolute path.
 ``` 
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{cKmcjGLoAWEgSXjqA9-6YfQUL1Z.QX5QTN0wyM0AzNzEzW}
hacker@paths~implicit-relative-paths-from-:/$  
```
### Challenge 7:
  **Flag**  pwn.college{onS1RTriuJgL_UNT0D1RPalMuOx.QXwUTN0wyM0AzNzEzW}
  Here we are running a command to invoke a program in a root directory using . in relative paths.
 ``` 
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{onS1RTriuJgL_UNT0D1RPalMuOx.QXwUTN0wyM0AzNzEzW}
hacker@paths~explicit-relative-paths-from-:/$ 
```
### Challenge 8:
  **Flag**  pwn.college{IESkjOO__A-ruad9QzHSOOrgmqV.QXxUTN0wyM0AzNzEzW}
  Here we are running a command to invoke a program from within the directory using relative path and . symbol.
 ``` 
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{IESkjOO__A-ruad9QzHSOOrgmqV.QXxUTN0wyM0AzNzEzW}
hacker@paths~implicit-relative-path:/challenge$ 
```
### Challenge 9:
  **Flag**  pwn.college{APyh8cl-keoMDKWO7w8sSpSj7rb.QXzMDO0wyM0AzNzEzW}
  Here we are running a command to invoke a program in a specified directory but an argument is added in the home directory to save a copy of the flag in the home directory.
 ``` 
hacker@paths~home-sweet-home:~$ /challenge/run ~/r
Writing the file to /home/hacker/r!
... and reading it back to you:
pwn.college{APyh8cl-keoMDKWO7w8sSpSj7rb.QXzMDO0wyM0AzNzEzW}
hacker@paths~home-sweet-home:~$ 
```

  
## What I learned
explain what you learned

## References 
Add any references or videos u used while solving the challenge.
