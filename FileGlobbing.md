# Linux Luminarium- File Globbing
The challenge helps to check documents to help while writing programs. These documents give instructions on how to use programs.

## My solve
### Challenge 1:
  **Flag**  pwn.college{QwMVL-R45nnXda7xJQGrphDjBxG.QXxIDO0wyM0AzNzEzW}
 To use the glob character * in a command. This is used to replace an argument with files of similar name pattern.So instead of typing the whole name we can use a part of it and use glob character.
 ``` 
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{QwMVL-R45nnXda7xJQGrphDjBxG.QXxIDO0wyM0AzNzEzW}
hacker@globbing~matching-with-:/challenge$ 
```
## What I learned
To use file globbing in linux terminal.

### Challenge 2:
  **Flag**  pwn.college{shoIvKMLbcH-X9OlNsb7nQJoibs.QXyIDO0wyM0AzNzEzW}
 Here we are using the ? argument which replaces a single character in a file or directory name.
 ``` 
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{shoIvKMLbcH-X9OlNsb7nQJoibs.QXyIDO0wyM0AzNzEzW}
hacker@globbing~matching-with-:/challenge$ 
```
## What I learned
To use the glob ? character in linux.
### Challenge 3:
  **Flag**  pwn.college{04E0o-gm-BSu-8ManGN4M_QwFEI.QXzIDO0wyM0AzNzEzW}
Here we are using the [] glob characters to specify the characters to check. This is like a limited version of the ? character.
 ``` 
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{04E0o-gm-BSu-8ManGN4M_QwFEI.QXzIDO0wyM0AzNzEzW}
hacker@globbing~matching-with-:/challenge/files$
```
## What I learned
To use the [] argument in linux to specify the characters to check for.

### Challenge 4:
  **Flag** pwn.college{Mo-AIj0qNzFSNaLA-KGIiv1Z3qF.QX0IDO0wyM0AzNzEzW}
 Here we use the [] command without entering the directory and got the flag.
 ``` 
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash] 
You got it! Here is your flag!
pwn.college{Mo-AIj0qNzFSNaLA-KGIiv1Z3qF.QX0IDO0wyM0AzNzEzW}
hacker@globbing~matching-paths-with-:~$ 
```
## What I learned
To use the [] glob to run program without entering the directory.

### Challenge 5:
  **Flag**  pwn.college{IgaOoEbzbnNCaVCZxZ_MbFPk_oT.0lM3kjNxwyM0AzNzEzW}
  
Here we are using the * command twice to find file names which have the letter p anywhere in their names.
 ``` 
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{IgaOoEbzbnNCaVCZxZ_MbFPk_oT.0lM3kjNxwyM0AzNzEzW}
hacker@globbing~multiple-globs:/challenge/files$
```
## What I learned
To use multiple glob characters in a single argument

### Challenge 6:
  **Flag**  pwn.college{QpsCnpxYmtrOiwXVK8Q_A3NR_bZ.QX1IDO0wyM0AzNzEzW}
 Here we are using the glob commands to write an argument under a set number of characters which only isolates particular items from a list.
 ``` 
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{QpsCnpxYmtrOiwXVK8Q_A3NR_bZ.QX1IDO0wyM0AzNzEzW}
hacker@globbing~mixing-globs:/challenge/files$ 
```
## What I learned
To use various file globbbing characters to get the required files.

### Challenge 7:
  **Flag**  pwn.college{YzBZaQsg96nyfQxSeo9mlxNqc31.QX2IDO0wyM0AzNzEzW}
Here we are using the ! as the negation of the previous [] glob argument.
 ``` 
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{YzBZaQsg96nyfQxSeo9mlxNqc31.QX2IDO0wyM0AzNzEzW}
hacker@globbing~exclusionary-globbing:/challenge/files$ 
```
## What I learned
The use of ! in glob

## References
None

