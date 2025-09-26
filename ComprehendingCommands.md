# Linux Luminarium- Comprehending Commands
The challenge helps to get familiar with useful and important Linux commands.

## My solve
### Challenge 1:
  **Flag**  pwn.college{MIpbHAWUfq7b2IdYgLgFPpEKJme.QXxcTN0wyM0AzNzEzW}
  Here we are running a command to read files.
 ``` 
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{MIpbHAWUfq7b2IdYgLgFPpEKJme.QXxcTN0wyM0AzNzEzW}
hacker@commands~cat-not-the-pet-but-the-command:~$ 
```
## What I learned
Here I learned the about the cat command and how to read a file.

### Challenge 2:
  **Flag**  pwn.college{AQAZtCoeIYY5dhCU9QhMl-h4EVM.QX5ETO0wyM0AzNzEzW}
  Here we are running cat command to read a file from an absolute path.
 ``` 
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{AQAZtCoeIYY5dhCU9QhMl-h4EVM.QX5ETO0wyM0AzNzEzW}
hacker@commands~catting-absolute-paths:~$ 
```
## What I learned
Learned to read a file from an absolute path.

### Challenge 3:
  **Flag**  pwn.college{EqrzukDHMj9FPBupdsKVGUVrphh.QXwITO0wyM0AzNzEzW}
  Here we are reading a file using absolute path without entering the directory.
 ``` 
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /lib/python3.8/sqlite3/flag. Go cat it out **without** cding into 
that directory!
hacker@commands~more-catting-practice:~$ cat /lib/python3.8/sqlite3/flag
pwn.college{EqrzukDHMj9FPBupdsKVGUVrphh.QXwITO0wyM0AzNzEzW}
hacker@commands~more-catting-practice:~$ 
```
## What I learned
To use the cat command to read a file without entering the directory using the cd command and by using absolute path.

### Challenge 4:
  **Flag**  pwn.college{MTr6O4yFs6iMKdCPCSp8iuAdlEj.QX3EDO0wyM0AzNzEzW}
  Here we are using grep command to read and print lines from large files instead of cat by searching for specific strings in the file.The grep command matches with my requirement and selects the lines from the  file.
 ``` 
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{MTr6O4yFs6iMKdCPCSp8iuAdlEj.QX3EDO0wyM0AzNzEzW}
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ 
```
## What I learned
To use grep command to read lines from larger files with a specific string.

### Challenge 5:
  **Flag**  pwn.college{QwlL9Tqcytjy5tW3xsEOgrIeSVj.01MwMDOxwyM0AzNzEzW}
  Here we are using the diff command to differentiate between two files line by line. This command shows the correct difference between the two files.Here 71a72 means there is a line 72 after kine 71 of file 1
 ``` 
hacker@commands~comparing-files:~$ cd /challenge
hacker@commands~comparing-files:/challenge$ diff decoys_only.txt decoys_and_real.txt
71a72
> pwn.college{QwlL9Tqcytjy5tW3xsEOgrIeSVj.01MwMDOxwyM0AzNzEzW}
hacker@commands~comparing-files:/challenge$ 
```
## What I learned
To check the difference between two files using the diff command.

### Challenge 6:
  **Flag**  pwn.college{w1bs0j0rh97ip1USOT0fKJIzsSF.QX4IDO0wyM0AzNzEzW}
  Here we are using ls command to list the files in a directory.
 ``` 
hacker@commands~listing-files:~$ cd /challenge
hacker@commands~listing-files:/challenge$ ls
7931-renamed-run-10615  DESCRIPTION.md
hacker@commands~listing-files:/challenge$ ./7931-renamed-run-10615
Yahaha, you found me! Here is your flag:
pwn.college{w1bs0j0rh97ip1USOT0fKJIzsSF.QX4IDO0wyM0AzNzEzW}
hacker@commands~listing-files:/challenge$ 
```
## What I learned
To use ls commmand to list the files in a directory.

### Challenge 7:
  **Flag**  pwn.college{EaI4QUxG67m1-Mkp8Mgyre8QyBA.QXwMDO0wyM0AzNzEzW}
  Here we are creating a new file using the touch command. This command creates a new blank file.
 ``` 
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ cd /challenge
hacker@commands~touching-files:/challenge$ ./run
Success! Here is your flag:
pwn.college{EaI4QUxG67m1-Mkp8Mgyre8QyBA.QXwMDO0wyM0AzNzEzW}
hacker@commands~touching-files:/challenge$
```
## What I learned
To create a new blank file using touch command.

### Challenge 8:
  **Flag**  pwn.college{Q8p1fdstob4j-MhCSoxSl-4b7et.QX2kDM1wyM0AzNzEzW}
Here we are creating a file delete_me then deleting it using the rm command. 
 ``` 
hacker@commands~removing-files:~$ touch delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls
h  r
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{Q8p1fdstob4j-MhCSoxSl-4b7et.QX2kDM1wyM0AzNzEzW}
hacker@commands~removing-files:~$ 
```
## What I learned
To use the rm command to delete a file in a directory.

### Challenge 9:
  **Flag**  pwn.college{MTk8R-lN-oUX3YdJlHgi01fIr0J.0VOxEzNxwyM0AzNzEzW}
 Here we are using the mv command to move a file from one directory to another. The first argument is the source directory and the second argument is the destination.
 ``` 
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{MTk8R-lN-oUX3YdJlHgi01fIr0J.0VOxEzNxwyM0AzNzEzW}

hacker@commands~moving-files:~$ 

```
  
## What I learned
To move a file from one directory to another using the mv commmand.

### Challenge 10:
  **Flag**  pwn.college{0GcmQ2cDqCZG0ILLmh9_RE-gkEF.QXwUDO0wyM0AzNzEzW}
  Here we are using the ls command with an attribute -a to display the files which start with . as they dont show up when we use ls without attribute. We're listing the files using ls -a and then reading the flag.
 ``` 
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv             bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-187641456728822  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ cat .flag-187641456728822
pwn.college{0GcmQ2cDqCZG0ILLmh9_RE-gkEF.QXwUDO0wyM0AzNzEzW}
hacker@commands~hidden-files:/$ 
```
  
## What I learned
To use -a attribute with ls to list all files in a directory.

### Challenge 11:
  **Flag**  pwn.college{MTAXLyO2rxNvjYfq1byS-xqLBo2.QX5IDO0wyM0AzNzEzW}
  
 Here in this program we accessed various files in different directories to get the flags. Here in some cases we entered the directory and then read the files and in other cases we listed the items in the directory without entering it and we read the file.
 ``` 
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
INFO  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat INFO
Tubular find!
The next clue is in: /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib$ ls
Age    BidiC  Bpt  CWCF   CWL  Cased   DI    Dia  Ext  GrBase  Hst     IDS   InPC  Jt     Math   NFKCQC  Nv      Perl   SD     Scx   UIdeo  WB
Alpha  BidiM  CE   CWCM   CWT  Ccc     Dash  Dt   GCB  GrExt   Hyphen  Ideo  InSC  Lb     NFCQC  NFKDQC  PCM     QMark  STerm  TIP   Upper  XIDC
Bc     Blk    CI   CWKCF  CWU  CompEx  Dep   Ea   Gc   Hex     IDC     In    Jg    Lower  NFDQC  Nt      PatSyn  SB     Sc     Term  Vo     XIDS
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib$ cat TIP
Great sleuthing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/numpy/testing
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib$ cd /usr/local/lib/python3.8/dist-packages/numpy/testing
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/numpy/testing$ ls
NUGGET  __init__.py  __init__.pyi  __pycache__  _private  print_coercion_tables.py  setup.py  tests  utils.py
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/numpy/testing$ cat NUGGET
Great sleuthing!
The next clue is in: /usr/lib/python3/dist-packages/sage/rings/finite_rings/__pycache__

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/numpy/testing$ ls /usr/lib/python3/dist-packages/sage/rings/finite_rings/__pycache__
TEASER-TRAPPED           conway_polynomials.cpython-38.pyc        finite_field_ntl_gf2e.cpython-38.pyc    homset.cpython-38.pyc
__init__.cpython-38.pyc  finite_field_constructor.cpython-38.pyc  finite_field_pari_ffelt.cpython-38.pyc  integer_mod_ring.cpython-38.pyc
all.cpython-38.pyc       finite_field_givaro.cpython-38.pyc       finite_field_prime_modn.cpython-38.pyc  maps_finite_field.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/numpy/testing$ cat /usr/lib/python3/dist-packages/sage/rings/finite_rings/__pycache__/TEASER-TRAPPED
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/drivers/net/ethernet/hp

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/numpy/testing$ cd /opt/linux/linux-5.4/drivers/net/ethernet/hp
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/hp$ ls
EVIDENCE  Kconfig  Makefile  built-in.a  hp100.c  hp100.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/hp$ cat EVIDENCE
Tubular find!
The next clue is in: /opt/busybox/busybox-1.33.2/examples/var_service/httpd

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/hp$ cd /opt/busybox/busybox-1.33.2/examples/var_service/httpd
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/examples/var_service/httpd$ ls
MEMO  log  run
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/examples/var_service/httpd$ cat MEMO
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/examples/var_service/httpd$ ls -a /usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__
.   .REVELATION              options.cpython-38.pyc      remote_connection.cpython-38.pyc  webdriver.cpython-38.pyc
..  __init__.cpython-38.pyc  permissions.cpython-38.pyc  service.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/examples/var_service/httpd$ cat /usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__ /.REVELATION
cat: /usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__: Is a directory
cat: /.REVELATION: No such file or directory
hacker@commands~an-epic-filesystem-quest:/opt/busybox/busybox-1.33.2/examples/var_service/httpd$ cd /usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__$ ls -a
.   .REVELATION              options.cpython-38.pyc      remote_connection.cpython-38.pyc  webdriver.cpython-38.pyc
..  __init__.cpython-38.pyc  permissions.cpython-38.pyc  service.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__$ ./.REVELATION
bash: ./.REVELATION: Permission denied
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__$ cat .REVELATION
Yahaha, you found me!
The next clue is in: /usr/share/man/nl/man7

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__$ ls -a /usr/share/man/nl/man7
.  ..  BRIEF-TRAPPED  deb-version.7.gz
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__$ cat /usr/share/man/nl/man7/BRIEF-TRAPPED
Tubular find!
The next clue is in: /usr/share/help/zh_TW

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/selenium/webdriver/safari/__pycache__$ cd /usr/share/help/zh_TW
hacker@commands~an-epic-filesystem-quest:/usr/share/help/zh_TW$ ls
DOSSIER  gedit
hacker@commands~an-epic-filesystem-quest:/usr/share/help/zh_TW$ cat DOSSIER
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{MTAXLyO2rxNvjYfq1byS-xqLBo2.QX5IDO0wyM0AzNzEzW}
hacker@commands~an-epic-filesystem-quest:/usr/share/help/zh_TW$ 

```
  
## What I learned
To read files without changing directories(trapped) and by entering the directory(delayed).Learned how to use the cd, cat, ls commands properly.

### Challenge 12:
  **Flag**  pwn.college{YtW-J2eGzHQi1slzlk3SybbRdcl.QXxMDO0wyM0AzNzEzW}
 Here we are using the mkdir command to create a file in a directory and then we are using the touch command to make a file in it.
 ``` 
hacker@commands~making-directories:~$ cd /tmp/pwn
bash: cd: /tmp/pwn: No such file or directory
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ cd
hacker@commands~making-directories:~$ /challenge/run
Success! Here is your flag:
pwn.college{YtW-J2eGzHQi1slzlk3SybbRdcl.QXxMDO0wyM0AzNzEzW}
hacker@commands~making-directories:~$ 
```
  
## What I learned
To create a new directory using the mkdir command.

### Challenge 13:
  **Flag**  pwn.college{IeY0vkMJ_PKGWqVdhitP9mf7lAo.QXyMDO0wyM0AzNzEzW}
Here we are using the find command to find the flag and reading it.
 ``` 
hacker@commands~finding-files:~$ cd /
hacker@commands~finding-files:/$ find -name flag
find: ‘./root’: Permission denied
find: ‘./etc/ssl/private’: Permission denied
find: ‘./tmp/tmp.4mK6TfTSUV’: Permission denied
./usr/local/lib/python3.8/dist-packages/pwnlib/flag
./usr/lib/python3/dist-packages/scipy/io/matlab/__pycache__/flag
find: ‘./var/cache/apt/archives/partial’: Permission denied
find: ‘./var/cache/ldconfig’: Permission denied
find: ‘./var/cache/private’: Permission denied
find: ‘./var/log/private’: Permission denied
find: ‘./var/log/apache2’: Permission denied
find: ‘./var/log/mysql’: Permission denied
find: ‘./var/lib/apt/lists/partial’: Permission denied
find: ‘./var/lib/mysql-keyring’: Permission denied
find: ‘./var/lib/php/sessions’: Permission denied
find: ‘./var/lib/private’: Permission denied
find: ‘./var/lib/mysql-files’: Permission denied
find: ‘./var/lib/mysql’: Permission denied
find: ‘./run/mysqld’: Permission denied
find: ‘./run/sudo’: Permission denied
find: ‘./proc/tty/driver’: Permission denied
find: ‘./proc/1/task/1/fd’: Permission denied
find: ‘./proc/1/task/1/fdinfo’: Permission denied
find: ‘./proc/1/task/1/ns’: Permission denied
find: ‘./proc/1/fd’: Permission denied
find: ‘./proc/1/map_files’: Permission denied
find: ‘./proc/1/fdinfo’: Permission denied
find: ‘./proc/1/ns’: Permission denied
find: ‘./proc/7/task/7/fd’: Permission denied
find: ‘./proc/7/task/7/fdinfo’: Permission denied
find: ‘./proc/7/task/7/ns’: Permission denied
find: ‘./proc/7/fd’: Permission denied
find: ‘./proc/7/map_files’: Permission denied
find: ‘./proc/7/fdinfo’: Permission denied
find: ‘./proc/7/ns’: Permission denied
./opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
./nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
./nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
./nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
./nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
./nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
./nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
./nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
./nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:/$ cd /usr/local/lib/python3.8/dist-packages/pwnlib/flag
hacker@commands~finding-files:/usr/local/lib/python3.8/dist-packages/pwnlib/flag$ cd
hacker@commands~finding-files:~$ cd /usr/lib/python3/dist-packages/scipy/io/matlab/__pycache__/
hacker@commands~finding-files:/usr/lib/python3/dist-packages/scipy/io/matlab/__pycache__$ ls
__init__.cpython-38.pyc        flag                mio4.cpython-38.pyc  mio5_params.cpython-38.pyc
byteordercodes.cpython-38.pyc  mio.cpython-38.pyc  mio5.cpython-38.pyc  miobase.cpython-38.pyc
hacker@commands~finding-files:/usr/lib/python3/dist-packages/scipy/io/matlab/__pycache__$ cat flag
pwn.college{IeY0vkMJ_PKGWqVdhitP9mf7lAo.QXyMDO0wyM0AzNzEzW}hacker@commands~finding-files:/usr/lib/python3/dist-packages/scipy/io/matlab/__pycache__$ 

```
  
## What I learned
To use the find command and the name attribute to find a particular file.

### Challenge 14:
  **Flag**  pwn.college{cdlcN6oz_EUfWYyxVA5B7nIwWJb.QX5ETN1wyM0AzNzEzW}
Using linking ln -s command to fool the computer into reading the flag.
 ``` 
hacker@commands~linking-files:~$ cd /home/hacker
hacker@commands~linking-files:~$ cd /home/hacker/
hacker@commands~linking-files:~$ cd /
hacker@commands~linking-files:/$ ld
/nix/store/mkvc0lnnpmi604rqsjdlv1pmhr638nbd-binutils-2.44/bin/ld: no input files
hacker@commands~linking-files:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~linking-files:/$ cd home
hacker@commands~linking-files:/home$ ls
hacker
hacker@commands~linking-files:/home$ cd hacker
hacker@commands~linking-files:~$ ls
h  not-the-flag  r
hacker@commands~linking-files:~$ rm not-the-flag
hacker@commands~linking-files:~$ ln -s /flag not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{cdlcN6oz_EUfWYyxVA5B7nIwWJb.QX5ETN1wyM0AzNzEzW}
hacker@commands~linking-files:~$ 

```
  
## What I learned
To use the ln -s command to create symlinks.

## References 
pwn.college video
https://www.youtube.com/watch?v=m55AtwjBXpE&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC
