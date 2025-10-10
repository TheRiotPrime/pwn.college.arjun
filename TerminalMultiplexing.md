# Linux Luminarium- Terminal Multiplexing

## My solve
### Challenge 1:
  **Flag**  pwn.college{8K9YFpo7eOWwWSsG3GrpNb9KWau.QX1UDO0wyM0AzNzEzW}
To open a screen in linux terminal. A screen is a virtual terminal inside the terminal.
 ``` 
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{8K9YFpo7eOWwWSsG3GrpNb9KWau.QX1UDO0wyM0AzNzEzW}
hacker@chaining~chaining-with-semicolons:~$ 
```
## What I learned
To use screen command.

### Challenge 2:
  **Flag** pwn.college{Qx8WDtqMDqD_xL1mMZPSyvTS0FZ.0lN4IDOxwyM0AzNzEzW}
 Here we are running a screen then detaching it and then we are running the run program and then reattaching the screen to get the flag.
 ``` 
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{Qx8WDtqMDqD_xL1mMZPSyvTS0FZ.0lN4IDOxwyM0AzNzEzW}
Yes! Flag is: pwn.college{Qx8WDtqMDqD_xL1mMZPSyvTS0FZ.0lN4IDOxwyM0AzNzEzW}
hacker@terminal-multiplexing~detaching-and-attaching:~$
```
## What I learned
To detach and reattach screen.

### Challenge 3:
  **Flag**  pwn.college{IT4YoAmOIPAwdcu7KmVgaUR9i7M.01N4IDOxwyM0AzNzEzW}
  Here we are listing the screens and finding the right one with the flag.
 ``` 
hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{IT4YoAmOIPAwdcu7KmVgaUR9i7M.01N4IDOxwyM0AzNzEzW}
pwn.college{IT4YoAmOIPAwdcu7KmVgaUR9i7M.01N4IDOxwyM0AzNzEzW}
hacker@terminal-multiplexing~finding-sessions:~$ 

```
## What I learned
To list and enter particular screen.

### Challenge 4:
  **Flag**  pwn.college{grfdzNtLbDE9c3TmutJ4vtIdgeO.0FO4IDOxwyM0AzNzEzW}
Here we are switching windows within the screen. We are going from windows 1 to window 0 so as to get the flag.
``` 
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{grfdzNtLbDE9c3TmutJ4vtIdgeO.0FO4IDOxwyM0AzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{grfdzNtLbDE9c3TmutJ4vtIdgeO.0FO4IDOxwyM0AzNzEzW}
hacker@terminal-multiplexing~switching-windows:~$ 
```
## What I learned
To switch windows among screens

### Challenge 5:
  **Flag**  pwn.college{04KCpgmnY4l2nzyIQQQO-vCn2d0.0VO4IDOxwyM0AzNzEzW}
 To use the tmux command instead of screen. We use Ctrl + B and d for detach and a for attach.
 ``` 
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{04KCpgmnY4l2nzyIQQQO-vCn2d0.0VO4IDOxwyM0AzNzEzW}
Congratulations, here is your flag: pwn.college{04KCpgmnY4l2nzyIQQQO-vCn2d0.0VO4IDOxwyM0AzNzEzW}
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ 

```
## What I learned
The tmux command.

### Challenge 6:
  **Flag** pwn.college{AfFgZhOGNVBP2YABlz6a_xPixiF.0FM5IDOxwyM0AzNzEzW}
 Here we are attaching the tmux windows and then switching to the windows 0 to get the flag by pressing Ctrl+B and then 0.
 ``` 
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{AfFgZhOGNVBP2YABlz6a_xPixiF.0FM5IDOxwyM0AzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{AfFgZhOGNVBP2YABlz6a_xPixiF.0FM5IDOxwyM0AzNzEzW}
hacker@terminal-multiplexing~switching-windows-tmux:~$ 
```
## What I learned
To change tmux windows

## References
None
