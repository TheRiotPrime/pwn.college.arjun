# Linux Luminarium- Practising Piping

## My solve
### Challenge 1:
  **Flag**  pwn.college{kOLgcZaG9_qp7k_PG6uo1chB6D-.QX0YTN0wyM0AzNzEzW}
 To use the the > redirection operator to redirect PWN to the file COLLEGE.
 ``` 
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{kOLgcZaG9_qp7k_PG6uo1chB6D-.QX0YTN0wyM0AzNzEzW}
hacker@piping~redirecting-output:~$ 
```
## What I learned
To use > commmand.

### Challenge 2:
  **Flag** pwn.college{IzLp8vE7hfdWfHK2ZtsB62TIapQ.QX1YTN0wyM0AzNzEzW}
 Here we are using the > argument to redirect the flag to a specific file.
 ``` 
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{IzLp8vE7hfdWfHK2ZtsB62TIapQ.QX1YTN0wyM0AzNzEzW}

hacker@piping~redirecting-more-output:~$ 
```
## What I learned
To use the > character to redirect the output of any command.

### Challenge 3:
  **Flag**  pwn.college{ooy55HGvUqPKQpcDscrE0oZXl40.QX3ATO0wyM0AzNzEzW}
  Here we are using the >> character to append instead of > which redirects as this prevents overwriting.
 ``` 
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
hacker@piping~appending-output:~$ cat the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{ooy55HGvUqPKQpcDscrE0oZXl40.QX3ATO0wyM0AzNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
hacker@piping~appending-output:~$ 
```
## What I learned
To use the >> appending character.

### Challenge 4:
  **Flag** pwn.college{4b9l6USgs9to2qlFZhE5n7eV6IO.QX3YTN0wyM0AzNzEzW}
 Here we use the File Descriptors to redirect the errors to instructions.
 ``` 
/hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{4b9l6USgs9to2qlFZhE5n7eV6IO.QX3YTN0wyM0AzNzEzW}

hacker@piping~redirecting-errors:~$ 
```
## What I learned
About the FD's in Linux.

### Challenge 5:
  **Flag**  pwn.college{o9c3S7cjT1D655VQshte_5uPqbT.QXwcTN0wyM0AzNzEzW}
  
Here we are using the > character to redirect input into the programs. Here we are redirecting the PWN file into the standard input.
 ``` 
hacker@piping~redirecting-input:~$ /challenge/run COLLEGE < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{o9c3S7cjT1D655VQshte_5uPqbT.QXwcTN0wyM0AzNzEzW}
hacker@piping~redirecting-input:~$
```
## What I learned
To use > character.

### Challenge 6:
  **Flag**  pwn.college{ItqoASqCe5UqhQvDMYFty8NU6lv.QX4EDO0wyM0AzNzEzW}
 Here we are using the > to redirect the output to a different file and using the grep command to search for the flag among the lines in the file.
 ``` 
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep "pwn" /tmp/data.txt
pwning
pwned
pwn.college{ItqoASqCe5UqhQvDMYFty8NU6lv.QX4EDO0wyM0AzNzEzW}
pwn
pwns
hacker@piping~grepping-stored-results:~$ 
```
## What I learned
To use grep command to search within a file.

### Challenge 7:
  **Flag**  pwn.college{4D5slG_GZDVhWQsKxkwN3CkmRHs.QX5EDO0wyM0AzNzEzW}
Here we are using the pipe | character. This helps to standard output on the left side to be piped into the standard input on the right side.
 ``` 
hacker@piping~grepping-live-output:~$ /challenge/run | grep "pwn"
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn
pwn.college{4D5slG_GZDVhWQsKxkwN3CkmRHs.QX5EDO0wyM0AzNzEzW}
pwns
pwning
pwned
hacker@piping~grepping-live-output:~$ 
```
## What I learned
The use of | in Linux.

### Challenge 8:
  **Flag**  pwn.college{YR8Vg_0rjB_OpODuFtGLmj8hf_N.QX1ATO0wyM0AzNzEzW}
Using the >& operator to convert standard error to standard output so as to use the grep command directly on errors.
 ``` 
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep "pwn"
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{YR8Vg_0rjB_OpODuFtGLmj8hf_N.QX1ATO0wyM0AzNzEzW}
pwning
pwned
pwn
pwns
hacker@piping~grepping-errors:~$ 
```
## What I learned
Using the >& operator in linux and to grep errors.

### Challenge 9:
  **Flag**  pwn.college{k6nzlXrxxuxeW6YkhzZVyZxmXRG.0FOxEzNxwyM0AzNzEzW}
  Here we are using the grep with -v argument so as to get the results which do not contain the particular pattern we mention.
 ``` 
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v "DECOY"
pwn.college{k6nzlXrxxuxeW6YkhzZVyZxmXRG.0FOxEzNxwyM0AzNzEzW}
hacker@piping~filtering-with-grep-v:~$ 
```
## What I learned
The use of -v attribute with the grep command.

### Challenge 10:
  **Flag**  pwn.college{QHDSiIggE7RcP9m7OSmxbXbAqNy.QXxITO0wyM0AzNzEzW}
Here we are using the pipe command and tee command to divert the output to a seperate file and read out the secret code which leads to the flag.
 ``` 
hacker@piping~duplicating-piped-data-with-tee:~$ touch file
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn |tee file |  /challenge/college
Processing...
WARNING: you are overwriting file file with tee's output...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat file
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "QHDSiIgg"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret QHDSiIgg | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{QHDSiIggE7RcP9m7OSmxbXbAqNy.QXxITO0wyM0AzNzEzW}
hacker@piping~duplicating-piped-data-with-tee:~$ 
```
## What I learned
To use the tee attribute while piping.

### Challenge 11:
  **Flag**  pwn.college{Eh46G_zi-lJ6FSFjvMFWzebmk8-.0lNwMDOxwyM0AzNzEzW}
Here we are using the diff command with the outputs which are considered as files using the <(command)  attribute.
 ``` 
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
'42a43
> pwn.college{Eh46G_zi-lJ6FSFjvMFWzebmk8-.0lNwMDOxwyM0AzNzEzW}
hacker@piping~process-substitution-for-input:~$ 
```
## What I learned
To use the <(command) attribute to convert outputs of commands to files so as to use them in file related commands(process substitutions).
