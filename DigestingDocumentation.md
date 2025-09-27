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

