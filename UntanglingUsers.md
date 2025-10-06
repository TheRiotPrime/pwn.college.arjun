# Linux Luminarium- Untangling Users

## My solve
### Challenge 1:
  **Flag**  pwn.college{svgn3Z3blKydZYC62GmQ2kNp3J5.QX1UDN1wyM0AzNzEzW}
  Here we are running the su command to get the root access with the pasword for authenticatrion and then running the flag program to get the flag with admin privileges.
 ``` 
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# ls
COLLEGE  Desktop  PWN  echo  file  h  instructions  myflag  not-the-flag  pwn  r  stdout  the-flag
root@users~becoming-root-with-su:/home/hacker# /challenge/run
It's not just hackers that need to become `root`.
Oftentimes, you, as the owner of your computer, need to use `root` access to administer it.
Becoming `root` is a fairly common action that Linux users take, and there are two utilities that exist for this purpose: `su` and `sudo`.

In this challenge, we will cover the older one, `su` (the **s**ubstitute **u**ser command).
This is not typically used to elevate to `root` access anymore, but it is an elegant utility from a more civilized time, and we'll cover it first.

`su` is a setuid binary:

```console
hacker@dojo:~$ ls -l /usr/bin/su
-rwsr-xr-x 1 root root 232416 Dec 1 11:45 /usr/bin/su
hacker@dojo:~$
```.

Because it has the SUID bit set, `su` runs as `root`.
Running as `root`, it can start a `root` shell!
Of course, `su` is discerning: before allowing the user to elevate privileges to `root`, it checks to make sure that the user knows the `root` password:

```console
hacker@dojo:~$ su
Password: 
su: Authentication failure
hacker@dojo:~$
```.

This check against the `root` password is what obsoletes `su`.
Modern systems very rarely have `root` passwords, and different mechanisms (that we will learn later) are used to grant administrative access.

But THIS challenge (and only this challenge) _does_ have a `root` password.
That password is `hack-the-planet`, and you must provide it to `su` to become `root`!
Go do that, and read the flag!
root@users~becoming-root-with-su:/home/hacker# cd
root@users~becoming-root-with-su:~# /challenge/run
It's not just hackers that need to become `root`.
Oftentimes, you, as the owner of your computer, need to use `root` access to administer it.
Becoming `root` is a fairly common action that Linux users take, and there are two utilities that exist for this purpose: `su` and `sudo`.

In this challenge, we will cover the older one, `su` (the **s**ubstitute **u**ser command).
This is not typically used to elevate to `root` access anymore, but it is an elegant utility from a more civilized time, and we'll cover it first.

`su` is a setuid binary:

```console
hacker@dojo:~$ ls -l /usr/bin/su
-rwsr-xr-x 1 root root 232416 Dec 1 11:45 /usr/bin/su
hacker@dojo:~$
```.

Because it has the SUID bit set, `su` runs as `root`.
Running as `root`, it can start a `root` shell!
Of course, `su` is discerning: before allowing the user to elevate privileges to `root`, it checks to make sure that the user knows the `root` password:

```console
hacker@dojo:~$ su
Password: 
su: Authentication failure
hacker@dojo:~$
```.

This check against the `root` password is what obsoletes `su`.
Modern systems very rarely have `root` passwords, and different mechanisms (that we will learn later) are used to grant administrative access.

But THIS challenge (and only this challenge) _does_ have a `root` password.
That password is `hack-the-planet`, and you must provide it to `su` to become `root`!
Go do that, and read the flag!
root@users~becoming-root-with-su:~# cd /
root@users~becoming-root-with-su:/# ls -l
total 68
lrwxrwxrwx    1 root root    7 Apr  4  2025 bin -> usr/bin
drwxr-xr-x    2 root root 4096 Apr 15  2020 boot
drwxr-xr-x    1 root root 4096 Oct  6 05:58 challenge
drwxr-xr-x    6 root root  380 Oct  6 05:58 dev
drwxr-xr-x    1 root root 4096 Oct  6 05:58 etc
-r--------    1 root root   60 Oct  6 05:58 flag
drwxr-xr-x    1 root root 4096 Sep 26 17:24 home
lrwxrwxrwx    1 root root    7 Apr  4  2025 lib -> usr/lib
lrwxrwxrwx    1 root root    9 Apr  4  2025 lib32 -> usr/lib32
lrwxrwxrwx    1 root root    9 Apr  4  2025 lib64 -> usr/lib64
lrwxrwxrwx    1 root root   10 Apr  4  2025 libx32 -> usr/libx32
drwxr-xr-x    2 root root 4096 Apr  4  2025 media
drwxr-xr-x    2 root root 4096 Apr  4  2025 mnt
drwxr-xr-x    1 root root   16 Oct 26  2024 nix
drwxr-xr-x    1 root root 4096 Sep 26 17:24 opt
dr-xr-xr-x 2615 root root    0 Oct  6 05:58 proc
drwx------    1 root root 4096 Sep 26 17:24 root
drwxr-xr-x    1 root root 4096 Oct  6 05:58 run
lrwxrwxrwx    1 root root    8 Apr  4  2025 sbin -> usr/sbin
drwxr-xr-x    2 root root 4096 Apr  4  2025 srv
dr-xr-xr-x   13 root root    0 Aug 27 03:13 sys
drwxrwxrwt    1 root root 4096 Oct  6 05:58 tmp
drwxr-xr-x    1 root root 4096 Sep 26 17:09 usr
drwxr-xr-x    1 root root 4096 Sep 26 17:08 var
root@users~becoming-root-with-su:/# cat flag
pwn.college{svgn3Z3blKydZYC62GmQ2kNp3J5.QX1UDN1wyM0AzNzEzW}
root@users~becoming-root-with-su:/# 
```
## What I learned
To use the su to get root access.

### Challenge 2:
  **Flag**  pwn.college{sFlE8KLOt4XPJDol0L_XnV-WmDJ.QX2UDN1wyM0AzNzEzW}
  Here we are using the su command with argument of the username zardus. Then we are running the run program to get the flag from within the root accessed user.
 ``` 
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{sFlE8KLOt4XPJDol0L_XnV-WmDJ.QX2UDN1wyM0AzNzEzW}
zardus@users~other-users-with-su:/home/hacker$ 
```
## What I learned
Learned to use su with username.

### Challenge 3:
  **Flag**  pwn.college{EiZ__tR7nBaTmKGY0lCu0nw2UX6.QX3UDN1wyM0AzNzEzW}
  Here we are give the /etc/shadow file leak through the /etc/shadow-leak file and then we are using thw john command to crack the password. After that we are logging in as root in the zardus user and running the run program to get the flag
 ```
 hacker@users~cracking-passwords:~$ /challenge/shadow-leak
bash: /challenge/shadow-leak: Permission denied
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:05 61% 1/3 0g/s 285.1p/s 285.1c/s 285.1C/s zardus80..Zardus75
0g 0:00:00:12 0% 2/3 0g/s 280.1p/s 280.1c/s 280.1C/s brenda..keith
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04861g/s 283.0p/s 283.0c/s 283.0C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ john --show
Password files required, but none specified
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak --show
hacker:NO PASSWORD:20357:0:99999:7:::
zardus:aardvark:20367:0:99999:7:::

2 password hashes cracked, 0 left
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{EiZ__tR7nBaTmKGY0lCu0nw2UX6.QX3UDN1wyM0AzNzEzW}
zardus@users~cracking-passwords:/home/hacker$ 
```
## What I learned
To use the john command to crack passowrds and about /etc/shadow

### Challenge 4:
  **Flag**  pwn.college{AabLZwvLHBFd_S5yJ7V1d2DbYp4.QX4UDN1wyM0AzNzEzW}
  Here we are using the sudo command to perform a command as root. We are reading the flag with sudo permissions.
 ``` 
hacker@users~using-sudo:~$ ls
COLLEGE  Desktop  PWN  echo  file  h  instructions  myflag  not-the-flag  pwn  r  stdout  the-flag
hacker@users~using-sudo:~$ cd /
hacker@users~using-sudo:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@users~using-sudo:/$ sudo flag
sudo: flag: command not found
hacker@users~using-sudo:/$ sudo cat flag
pwn.college{AabLZwvLHBFd_S5yJ7V1d2DbYp4.QX4UDN1wyM0AzNzEzW}
hacker@users~using-sudo:/$ 
```
## What I learned
The sudo command.

## References 
None
