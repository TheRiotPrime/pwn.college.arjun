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

### Challenge 5:
  **Flag**  pwn.college{YqGMX0Y-Y0tgkHB5gsQX40MJPtK.01NxEzNxwyM0AzNzEzW}
Here we are using the cut command to select the second part of the line which contains the flag and using the tr command to remove the newline spaces. 
 ``` 
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run
7400 p
27461 w
599 n
18870 .
27507 c
19790 o
31419 l
4197 l
32110 e
27190 g
1158 e
12716 {
13184 Y
18112 q
27996 G
13078 M
1384 X
10382 0
15222 Y
28869 -
9656 Y
32335 0
8459 t
27343 g
26976 k
21972 H
2254 B
8447 5
32048 g
4872 s
8283 Q
27665 X
26089 4
18697 0
1269 M
7080 J
25498 P
18995 t
1115 K
30240 .
16230 0
24393 1
21819 N
20216 x
6814 E
136 z
28845 N
5055 x
6624 w
22330 y
16191 M
22766 0
7846 A
20097 z
2930 N
5438 z
23070 E
30381 z
26818 W
12908 }
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d  " " -f 2 | tr -d "\n"
pwn.college{YqGMX0Y-Y0tgkHB5gsQX40MJPtK.01NxEzNxwyM0AzNzEzW}hacker@data~extracting-specific-sections-of-text:~$ 
```
## What I learned
To use the cut command in Linux

### Challenge 6:
  **Flag**  pwn.college{4z2smCBNYRAtFPILCK6G4XK7-Ei.0FNxEzNxwyM0AzNzEzW}
  Here we are using the sort command to sort ouyt the flags. It is mentioned that the flag is at the end so we use the -r attribute which sorts the lines in the descending alphabetic order.
 ``` 
hacker@data~sorting-data:~$ sort /challenge/flags.txt -r
pwn.college{sMQ8ITXCLZFj_2KzkktnCatFPfK.0FM0MDOxwyM0AzNzEzW}
pwn.college{sMQ8ITXCLZFj_2KzkktnCatFPfK.0FM0MDOxwyM0AzNzEzW}
pwn.college{sMQ8ITXCLZFj_2KzkktnCatFPfK.0FM0MDOxwyM0AyNzEzW}
pwn.college{sMQ8ITXCLZFj_2KzkktnCatFPfK.0FM0LDOxwyM0AzNzEzW}
pwn.college{sMQ8ITXCLZFj_2KzkktnCatFPfK.0EM0LDOxwxM0AyMyEzW}
pwn.college{sMQ8ITXCLZFj_2KzkktnCatEPfK.0EM0MDOxwxL0AzNzEzW}
pwn.college{sMQ8ITXCLZFj_2KzkktnBatFPfK.0FM0MDOxwyM0AzNzDzW}
pwn.college{sMQ8ITXCLZFj_2KzkjtnCatFPfK.0FM0MDOxvyM0AzNzEzW}
pwn.college{sMQ8ITXCLZFj_2JzkktnCatFOfJ.0FM0MDOxwyM0AzNzEzW}
pwn.college{sMQ8ITXCKYEj_2JzkjtnCatFPfK.0FL0LDOxwyL0AzNyEyV}
pwn.college{sMQ8ISXCLZFj_2KzkktnCatFPfK.0FM0MDOxwyL0AzNzEzW}
pwn.college{sMP8ITXCLZFj_2KykktmCatFPfK.0FM0MCOxwxM0AzNzEzW}
pwn.college{sMP8ISXCLZEj_2KzkksnCatFPfK.0FM0MCOxvyM0AzNzEyW}
pwn.college{rMQ8ISXCLZFj_2KzkktnCatFPfK.0FM0MCOwwyM0AzNzEzW}
pwn.college{rMP8ITXCLZFj_1KzkktnBasFPfK.0EL0LCOxwyL0AzNzEzW}
pwn.collefe{sMQ8ITXCLZFj_2KzkktmCatFPfK.0FM0MDOxwyM0AzNzDzW}
pwn.collefe{sMQ8ITXCLZFj_2KzjktnCatFPfK.0FM0MDOxwyM0AzNzEyW}
pwn.collefe{sMQ8ITXCLYFj_1JzkktnCatFPfK.0FM0MDOxvxM0AzMzDzW}
pwn.collefe{sMQ8HTXCLYFj_2KzkjtnCatFPfK.0FM0MCOxwyL0AyNzEyW}
pwn.collefe{sLQ8HTXCKZFj_2JzkksmBatFPfK.0FM0LDOxwyM0AzNzEzW}
pwn.collefe{rMP8HTXCLZFj_2JyjktmCatFPfK.0EM0LDOxwyM0AzNzEzV}
pwn.colldge{sMQ8ITXCLZFj_2KzkktnCatFPfK.0FM0MDOxwyM0AzNzEzV}
pwn.colldge{rMP8ISXCKZFj_1JykksnCasEPfJ.0FL0LCOxwyL0AzMzDzW}
pwn.colkege{sMQ8ITXBLZFj_1JzjktnCatEPeJ.0EM0LDNwwyL0AzMzEyW}
pwn.colkege{sMQ7ITWCLZFj_2KzkksnBatFPfK.0FM0LDNwwyM0AzNyDzW}
pwn.colkege{sMP8ITXBLZEj_2KzkktnBatEPfK.0FL0MCOxvxL0AzMzEzW}
pwn.colkefe{sMQ8HTXCLZFj_1JzkktnCatFPfK.0FL0MDOxwxL0AzNzEzW}
pwn.colkefe{rLP7ITXCLYFj_2KzkjtnCatEPfK.0FM0MCOxwyM0AzMzEzW}
pwn.colkefd{rLQ8ITXBLYEi_2JzkktmCatEPeJ.0FM0MDNxvyM0AzMzEzV}
pwn.colkdge{sMQ8ITXCLZFi_2KzkktnCatFPfK.0FM0MDOxwyM0AzNzEzW}
pwn.colkdfe{sMP8ITWCLZFj_2KzjktnBasEOfK.0EM0MDOwwyM0AzNzEyW}
pwn.coklege{sMQ8ITXCLZFj_2KzkksnCatFPfK.0FM0MDOwwxM0AzNzDzW}
pwn.coklege{sMQ7HTXCLZFj_1JzjktnCatEPfJ.0FM0MDNxwyM0AzNzEyW}
pwn.coklege{sMP7ISXCLZFi_2JzkktnCatEPfK.0FM0MCOxvyL0AzNzEzW}
pwn.coklege{rLQ8ITXCKZFj_2JykktnCatFPfJ.0FL0MCNxvyM0AzNzEzW}
pwn.cokldfe{rMQ8HTXCKYEj_2KzjjtnCasEPeK.0FM0MDOxwyM0AzNzEyW}
pwn.cnllege{sMQ8ITXCLZFj_2KzjktnCatEPfK.0FM0LDOxwyM0AzNzEzW}
pwn.cnllege{sMQ8HSXBKZFj_1KykktnCatFPfJ.0FM0MCNxwyM0AzMzEzW}
pwn.cnllege{sMQ7ISWCLZFj_1KzkktmCatFPfJ.0FM0LDOxwyM0AzNyEzV}
pwn.cnlldgd{sLP7ISXCLZFi_1KyjksmCasFPfK.0EL0LCOxwyM0AzMyEzW}
pwn.cnkkdgd{rMP7ISWCKZFi_1KzkktnBasFPfK.0FL0MDNxwyM0AzMyDzW}
pwn.bollege{sMQ8ITXCLZEi_2KzkktnCatFPfK.0EM0MDOxwyM0AzNzEzW}
pwn.bollege{sMQ7HTXCKZFj_2KykktmCatFPfK.0FL0MDOxwyL0AzNyEzW}
pwn.bolldge{sMQ8HTWCLYFj_2JzkjsnCatEPeK.0FM0MDNxwyM0AzNzDzV}
pwn.bolldfd{rMQ7HTXCLZFj_2KykjtnBasFPeK.0EL0LCOxvyM0AyMyDzW}
pwn.bolkege{sMQ8ITXCLZFj_1KzjktnBatFPeK.0FM0LDOxwyM0AzNzEzW}
pwn.bolkege{sMQ8ISXCKZFj_2JzkktnBatFOfK.0FM0MDOwvxM0AzNzEyW}
pwn.bokkege{sMQ8ISXCLYEj_2JzjjtnCatFPfK.0FL0MDNwwxM0AzNzEzW}
pwm.college{sMQ8ITXCLZFj_2KzkktnCatFPfK.0FM0MDNxwyM0AzNzEzW}
pwm.college{sMQ8ITXCKZFi_2KzkktnCatFPeK.0FM0MDOxwxM0AzNzEzW}
pwm.college{sLQ8ITXCLZFi_2KzkktmCatFPfJ.0FM0MDOxvxM0AzMyDzV}
pwm.collegd{sMQ8HTWCLYEi_2KyjjtnCasEPfK.0FM0LDOxvyM0AyMzDzW}
pwm.collegd{sMP8ITWCLYFj_2JykjtnCatFPeK.0FL0MDOwwxM0AyNzEzW}
pwm.collefd{rMQ8HSXBKZEj_1KzkksnCasFPeK.0EM0LDOwwxM0AzNzDzW}
pwm.colkdge{sLP7HSXCLYFj_2KzkktmBatEOeJ.0FM0MCOxwyM0AzNzEyV}
pwm.coklege{sMQ8ITXBLZFj_2KzkktnCatFPeK.0FL0MDOxwyM0AzMzEyW}
pwm.cokkegd{rMQ8ITXCLZFj_2KykjtnCatFPfK.0FM0MDOxwyM0AzNzDyW}
pwm.cokkdfe{sMQ8ITXBLYFj_1KzkktnBatEOfK.0EM0MDOwwyM0AzNyDzW}
pwm.cnllege{sMQ8ITXCKZFi_2KzkktnCatFOfK.0FM0MCOxwyM0AyNzEyW}
pwm.cnllefe{rMP8HTXBLYEi_2KyjjtmCatEOfK.0FM0MCOxwyM0AzNzEzW}
pwm.cnllefd{sMP8ISXBKZFi_2KzkktnCasFOeJ.0FL0LCNxvxM0AyMzEzV}
pwm.cnlkege{sLQ7HTXCLZEi_1KykksnBatFPfK.0FL0MDOwwyM0AzNyDyV}
pwm.cnklefe{rMP8ISWBLZEj_2JzkjtnCatFPeK.0FM0MDNwwxM0AzNzEyV}
pvn.college{sMQ8ITXBKZFj_2KzkksnBatFOfJ.0FL0MDOxvyM0AyNzDzW}
pvn.collegd{sMQ8ITXCKZFi_2KzjktnCatFPfK.0FM0MDNxwyL0AzNzEzW}
pvn.collefe{rMQ7ITXBLZFj_2KykksnBasEPfK.0FM0LDOxvyM0AzNzEzV}
pvn.colkege{sMQ7ITWCLZFj_2KykktnCatFPeK.0FM0MDOxwyM0AzNzEzW}
pvn.colkdge{sMP7ITWCLZEi_1KzjjtnBatFPfK.0FM0LCNxwxL0AzNyDyW}
pvn.colkdfd{rMQ8HTXCKYEi_2JzkktnBatEPfK.0FM0LDOwwyM0AzMzEzW}
pvn.cokldge{sMQ8HTXCLYFj_2KzkktnCatFPfJ.0FM0LDOxwyM0AzNzEzW}
pvn.bolldfe{sMQ7ITXCLYEj_2KzkktnBasFOfK.0FL0MDNxwyM0AzNzDzW}
pvn.bolldfe{rMP8HTXCLYFj_2KzjktnBasFPfK.0EL0MCNxvyM0AzNzEzW}
pvm.collefe{sLP8ITWBKYFi_1KzkktmCatEPfK.0FM0MDOxvyM0AyNzEzW}
pvm.coklegd{sMQ8HSWCKZFj_2KykksnBasFPfK.0EM0MDOxwyM0AyMzEzV}
pvm.cnklefe{sLQ8HTXCLZFj_2JzkktnBasFOeK.0FM0LDNxwyM0AyNzDyW}
pvm.bollege{sMQ7ITXCLZFj_2KzjktmBatFOfJ.0FL0LDNxwxM0AzNzEyW}
pvm.bollegd{sMP8ITXCKZFj_1KzjjtnCatFPfK.0FM0MCOxwyM0AyNyDzW}
pvm.bnllegd{rMP8ITXCLZFi_2KzkktnCasEPfJ.0EM0LDOxwxM0AzNzEyW}
own.college{sLQ8ITXBLZFi_2KzjjtnCatFPfK.0FM0MDOwvyM0AzNzEzW}
own.collegd{sMQ8ITWCLZFi_2JzkktmCatEPfJ.0FM0MDOxwxM0AzNzEyW}
own.collegd{sLQ8ITXCLZFj_2JyjjtnCatFOfK.0FM0LCNxwyM0AyNzEzW}
own.colkege{rMQ8ITXCLZFj_2KykksnCatFPfK.0FM0MCOxwyM0AzNzEzW}
```
## What I learned
Learned to use the sort command to sort the lines of a file.


## References 
None
