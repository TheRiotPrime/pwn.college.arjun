# Linux Luminarium- Digesting Documentation
The challenge helps to check documents to help while writing programs. These documents give instructions on how to use programs.

## My solve
### Challenge 1:
  **Flag**  pwn.college{QaejwCsCXJWyh1IlxO2r6e34ltp.QX0ITO0wyM0AzNzEzW}
  Here we are running a program with an argument which would only give the flag if we use a specific argument.
 ``` 
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{QaejwCsCXJWyh1IlxO2r6e34ltp.QX0ITO0wyM0AzNzEzW}
hacker@man~learning-from-documentation:~$ 
```
## What I learned
To use arguments that are required for the proper output from the program.

### Challenge 2:
  **Flag**  pwn.college{gBByLiImyY5mg5ZzlgLPrq8UCm4.QX1ITO0wyM0AzNzEzW}
  Here we are using an argument which has another argument for itself. The program has a --printfile argument which has another argument which specifies the path to the flag.
 ``` 
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{gBByLiImyY5mg5ZzlgLPrq8UCm4.QX1ITO0wyM0AzNzEzW}
hacker@man~learning-complex-usage:~$ 
```
## What I learned
To nest arguments.
### Challenge 3:
  **Flag**  pwn.college{YJf88F-BUlmgXvc83YepNDaUFWa.QX0EDO0wyM0AzNzEzW}
 Here we are reading a manual to find the correct attribute which will give the flag.
 ``` 
hacker@man~reading-manuals:~$ /challenge/challenge --flmgvc 888
Correct usage! Your flag: pwn.college{YJf88F-BUlmgXvc83YepNDaUFWa.QX0EDO0wyM0AzNzEzW}
hacker@man~reading-manuals:~$ 
```
## What I learned
To read a manual to learn about a command and to use the man command properly.
### Challenge 4:
  **Flag**  pwn.college{I1BC-K62O_Fym29ANdC4ihUxPY3.QX1EDO0wyM0AzNzEzW}
 Here we read a manual of a command and search through it using the / command and moving to next search result using n.
 ``` 
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ man challenge 
hacker@man~searching-manuals:~$ /challenge --xaqyj
bash: /challenge: Is a directory
hacker@man~searching-manuals:~$ cd /challenge
hacker@man~searching-manuals:/challenge$ ls
DESCRIPTION.md  challenge
hacker@man~searching-manuals:/challenge$ /challenge/challenge --xaqyj
Initializing...
Correct usage! Your flag: pwn.college{I1BC-K62O_Fym29ANdC4ihUxPY3.QX1EDO0wyM0AzNzEzW}
hacker@man~searching-manuals:/challenge$ 
```
## What I learned
To search through a manual and to find specific attributes easily.
### Challenge 5:
  **Flag**  pwn.college{UIzXH7OJhLNu6GQp1CuUbT5W9Pb.QX2EDO0wyM0AzNzEzW}
  
  Here we are searching for a particular file associated with the term flag by following instructions from a manual.
 ``` 
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k flag
dpkg-buildflags (1)  - returns build flags to use during package build
Dpkg::BuildFlags (3perl) - query build flags
fegetexceptflag (3)  - floating-point rounding and exception handling
fesetexceptflag (3)  - floating-point rounding and exception handling
i386 (8)             - change reported architecture in new program environment and/or set personality flags
ioctl_iflags (2)     - ioctl() operations for inode flags
linux32 (1)          - change reported architecture in new program environment and/or set personality flags
linux64 (1)          - change reported architecture in new program environment and/or set personality flags
pcap-config (1)      - write libpcap compiler and linker flags to standard output
security_compute_av_flags (3) - query the SELinux policy database in the kernel
security_compute_av_flags_raw (3) - query the SELinux policy database in the kernel
set_matchpathcon_flags (3) - set flags controlling the operation of matchpathcon or matchpathcon_index and configure the behaviour of validity ...
set_matchpathcon_invalidcon (3) - set flags controlling the operation of matchpathcon or matchpathcon_index and configure the behaviour of vali...
set_matchpathcon_printf (3) - set flags controlling the operation of matchpathcon or matchpathcon_index and configure the behaviour of validity...
setarch (1)          - change reported architecture in new program environment and/or set personality flags
setarch (8)          - change reported architecture in new program environment and/or set personality flags
x86_64 (8)           - change reported architecture in new program environment and/or set personality flags
zhupubbwyz (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man zhupubbwyz
hacker@man~searching-for-manuals:~$ /challenge/challenge --zhupub 761
Correct usage! Your flag: pwn.college{UIzXH7OJhLNu6GQp1CuUbT5W9Pb.QX2EDO0wyM0AzNzEzW}
hacker@man~searching-for-manuals:~$ 
```
## What I learned
TO use the manual of a command properly and to search for requirements using the man command.

### Challenge 6:
  **Flag**  pwn.college{w3D19K2dt8vV_HxQM3UMi3ehQnv.QX3IDO0wyM0AzNzEzW}
 Here we are using the --help attribute to help in case there is no manual.The --help command leads us to the attributes which will give us the secret number and the flag finally.
 ``` 
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 319
hacker@man~helpful-programs:~$ /challenge/challenge -g 319
Correct usage! Your flag: pwn.college{w3D19K2dt8vV_HxQM3UMi3ehQnv.QX3IDO0wyM0AzNzEzW}
hacker@man~helpful-programs:~$ 
```
## What I learned
To use the --help command.
### Challenge 7:
  **Flag**  pwn.college{QUDV5RNleKs4JFLMKdvcqPLLff-.QX0ETO0wyM0AzNzEzW}
Here we are using the help command to see help info of builtins which are the commands that are in the shell handled internally.
 ``` 
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "QUDV5RNl".
hacker@man~help-for-builtins:~$ challenge --secret QUDV5RNl
Correct! Here is your flag!
pwn.college{QUDV5RNleKs4JFLMKdvcqPLLff-.QX0ETO0wyM0AzNzEzW}

hacker@man~help-for-builtins:~$ 
```
## What I learned
About builtins in shell

## References
None

