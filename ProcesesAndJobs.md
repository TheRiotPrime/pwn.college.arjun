# Linux Luminarium- Processes and Jobs

## My solve
### Challenge 1:
  **Flag**  pwn.college{QAr6-miKAEU2gksC_nB4ZoQkSUK.QX4MDO0wyM0AzNzEzW}
 To use the the ps command to list the processes. We use the -e argument to see the 'every process' and the -f argument to see the full foirmat. we use it together with ww to prevent truncation.
 ``` 
hacker@processes~listing-processes:~$ ps -efww
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 04:32 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 04:32 ?        00:00:00 /run/dojo/bin/sleep 6h
root         132       1  0 04:32 ?        00:00:00 /challenge/32232-run-15946
root         135     132  0 04:32 ?        00:00:00 sleep 6h
hacker       146       1  0 04:33 ?        00:00:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0.0 --writable -t disableLeaveAlert true /run/dojo/bin/bash --login
hacker       150     146  0 04:33 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       160     150  0 04:33 pts/0    00:00:00 ps -efww
hacker@processes~listing-processes:~$ /challenge/32232-run-15946
Yahaha, you found me! Here is your flag:
pwn.college{QAr6-miKAEU2gksC_nB4ZoQkSUK.QX4MDO0wyM0AzNzEzW}
Now I will sleep for a while (so that you could find me with 'ps'). 
```
## What I learned
To use the ps command to see the processes and to give arguments ef and aux to it to see required results.

### Challenge 2:
  **Flag** pwn.college{ca6XLASi_XfS5puAgcWwt2eF6qD.QXyQDO0wyM0AzNzEzW}
 Here we are using the kill command to kill the /challenge/dont_run. We first list the processes and find the process identifier using the ps command and then we'll use the kill command to kill the process. After that we run the /challenge/run command to get the flag.
 ``` 
hacker@processes~killing-processes:~$ ps -e | grep /challenge/dont_run
hacker@processes~killing-processes:~$ 
hacker@processes~killing-processes:~$ ps -e | grep /challenge/dont_run
hacker@processes~killing-processes:~$ ps -e
    PID TTY          TIME CMD
      1 ?        00:00:00 docker-init
      7 ?        00:00:00 /run/dojo/bin/s
    135 ?        00:00:00 su
    136 ?        00:00:00 bash
    137 ?        00:00:00 sleep
    148 ?        00:00:00 ttyd
    152 pts/0    00:00:00 bash
    166 pts/0    00:00:00 ps
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 04:38 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 04:38 ?        00:00:00 /run/dojo/bin/sleep 6h
root         135       1  0 04:38 ?        00:00:00 su -c /challenge/.launcher hacker
hacker       136     135  0 04:38 ?        00:00:00 /challenge/dont_run
hacker       137     136  0 04:38 ?        00:00:00 sleep 6h
hacker       148       1  0 04:38 ?        00:00:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0.
hacker       152     148  0 04:38 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       167     152  0 04:39 pts/0    00:00:00 ps -ef
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 04:38 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 04:38 ?        00:00:00 /run/dojo/bin/sleep 6h
hacker       137       1  0 04:38 ?        00:00:00 sleep 6h
hacker       148       1  0 04:38 ?        00:00:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0.
hacker       152     148  0 04:38 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       168     152  0 04:39 pts/0    00:00:00 ps -ef
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{ca6XLASi_XfS5puAgcWwt2eF6qD.QXyQDO0wyM0AzNzEzW}
hacker@processes~killing-processes:~$ 
```
## What I learned
To use the kill command to kill a process.

### Challenge 3:
  **Flag**  pwn.college{w-SlRC4fUrwRB8zcfKMU-5bocrn.QXzQDO0wyM0AzNzEzW}
  Here we are interrupting the /challenge/run to get the flag using Ctrl + C.
 ``` 
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{w-SlRC4fUrwRB8zcfKMU-5bocrn.QXzQDO0wyM0AzNzEzW}
hacker@processes~interrupting-processes:~$
```
## What I learned
To use the Ctrl + C to interrupt a process.

### Challenge 4:
  **Flag** pwn.college{wU1074mDVcUZeOmgdqt1nGLDHK4.0FNzMDOxwyM0AzNzEzW}
 Here we first list the processes and then we use the kill command to kill out the decoy process. Then we redirect the correct flag from /challenge/run to the flaG_fifo file.
 ``` 
hacker@processes~killing-misbehaving-processes:~$ ps -ef | grep /challenge/decoy
root         139       1  0 05:12 ?        00:00:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
hacker       142     139  0 05:12 ?        00:00:00 /usr/bin/python /challenge/decoy
hacker       168     157  0 05:12 pts/0    00:00:00 grep --color=auto /challenge/decoy
hacker@processes~killing-misbehaving-processes:~$ kill 142
hacker@processes~killing-misbehaving-processes:~$ ps -ef | grep /challenge/decoy
hacker       170     157  0 05:12 pts/0    00:00:00 grep --color=auto /challenge/decoy
hacker@processes~killing-misbehaving-processes:~$ cat /challenge/run
#!/opt/pwn.college/bash

fold -s <<< "Sending the flag to /tmp/flag_fifo!"
cat /flag > /tmp/flag_fifo
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{ukyJEUNpQd78lBt3mCY2LjYb8nlWVJRDwG-Oqia6fbmE-5o}
pwn.college{H3KGo4X.CR3G6R1DPSlRhBTNPFQo1eNt8zjgOsKZZsV16XE}
pwn.college{0qt1CUouzYaBUzkIuTeYiU369GYJkQ82yvtiWr8gVwl9qVM}
pwn.college{l6OYazc7WVaEmZVANpJJfZkoUpRRvNwxKefGYT6Rb-atO71}
pwn.college{aUOhCzjEOApkd6Ifwk1a1UhstvuuDYyE-rm0s3G8pORfYkZ}
pwn.college{kP74dXoitVP8WhPaiHt6ftfI82.VRbve8Dt3oybTqgZhlcv}
pwn.college{Z2q.vfHkVJjFiNnEio5IDKv6PjS7Yz9.YyjFNnrmbUsOmZc}
pwn.college{x.NKihdN2RV6d5RE33jKPaIsVqM6vz3wVF0ZF.Jxu9XsprZ}
pwn.college{Q0HZHyACV6135.MYU32mVgdvc5IGYf1KwncnRmsVVCYolHQ}
pwn.college{A0FaZVI08iPbDxeI5sru8sIyR3jgOSOwy.Hnmoxu.ZzFReq}
pwn.college{2uJz.xfPW5JFK5UPDeoxthbhsc4kBwriTDquNG6MzeBPQtx}
pwn.college{EdAUQZJGXQdWlXw.NIav42tdb7EWzEf3S3y1CXALKYFdcJY}
pwn.college{PLy-cHSHV61m6URzVI2Jfc7ub8VoOkM1s57azFXndpjYhD7}
pwn.college{nwEfHdOyOeoiRp.s4bjR1RIEUX.AnT-2ja6k17hYX.lmgOz}
pwn.college{RyIDWW26-u0uXhxT65U-NeuGls0CUnxXHuz2ZPJ6RcA2Loh}
pwn.college{r6vBP2N9bmUKYcy7UWr7kkADBS-X5UfiaoPZFT4DLgVz29f}
pwn.college{sg8usTywZrtS18aHJgA0yMTAhY5oRLDgHobM.49CEF6tBwM}
pwn.college{nQxELwY6USh0nDfl7UXc3x1S-7tj6xhRB5SR2kxWi2LamqE}
pwn.college{BsOpEwg0oBPNQnY1bfDtbREXSmNfticBeZJ3N6TDhor6z3H}
pwn.college{cd3LBsBb4Q1smvMhKvUWI2pHPK4qyOv3z9owhDmrxH.ZPQl}
pwn.college{94XgEUDhS2T1kO4fvzAkvH3XOMZSwyR4kugo9bcWn4hAExc}
pwn.college{xy71o-8rQa0.Kr3.ZLTSrgnHzzcGRIbHFGukpUHByOyoCH-}
pwn.college{L0BMCthjgDfMbVUyD0iJAnAAQ5k9qTj5HUxXVKXayIVlxsy}
pwn.college{f8TO1Yf3SHc35G4UxYFplalFz3n4Ff00ieuMQqtLd63T9Zg}
pwn.college{UfFiuwY6p9j.beL4-nCIZ31SVDD-6rzT49CqvNs7yEt-BZ2}
pwn.college{830pxpa2sk-Zm1CA-4eN3MYg1jeU7.gGA6hE.-pWHuLr.mA}
pwn.college{d3gt9TN6TnlpthM4Ed9dTkVD94Hcu6IYw11DJNR9D9dUBFm}
pwn.college{r7AQxzI.DB-dxrOSI6ssK4UVS3fbyrets7Dp0AjSrFvH4Ya}
pwn.college{uzTxmw7A-BmSaePfFRKX3GZ1NO8Kn1UmTNiyD3DXaiu8jQd}
pwn.college{4XOLM-0vpxUF745jiUi0jQJEoTSJ0sCNr8zfa0QFtvzr.KB}
pwn.college{FLwO3iSzE-hTo0y8aP4YRUVhlUUOzi7WUqZDwcEVhGmomHh}
pwn.college{olVaq3qDoQKR2EcFQHAjP94RP2wsY0oDeqcsDzxAaWQcnD9}
pwn.college{sqawxlGQPMosNSZn.yoBatgLMBBdGHlc2tiuZHiuRBqoLa4}
pwn.college{xZ5ZKUubexZSXMRD6qSdxBFabjPSmUA5TaYZrv72fn.StBb}
pwn.college{iz09qdaoH51XIB.0K9jzAOIXFSSPPVbC8NdLexgxunczr0P}
pwn.college{FIrZdUIEdVUTWIRdO5yFBt9k0Cg2TllZPpGyeETOvKesdnr}
pwn.college{tVvQTNuDiQ4fonMW.og7bETozRMrzwGaadXftPbZUp7DYXE}
pwn.college{.eiZGIOG03D.A--.m67H7Ch3vOtSB2F5G0sDG6HAR-7Aej7}
pwn.college{WJ6xCav51d7lU3acwa8N2FWt4kzaWyZwcSsd1QhPSfwPvzh}
pwn.college{SRiKVttSQ-oybmdA8PI6A7tCOFTHCsVLjgRWvQIXNOc8Tr7}
pwn.college{lnFsG7MX5iCZN3hLrFRHdRlfFV5d67nLKV6vdA1WhkeJCya}
pwn.college{cQRqxlTG0fvo3lZg6.3Lj2tCwok9BX2A47A0ae66jtPAGbD}
pwn.college{NQ3WzCvo10H61SpuUwhE7YV0.-0t-.KFVfNQuMQKrjpJ92e}
pwn.college{wvfwylklEfJPwMXbLTsBUJ60Zq9aw4zhC4JFYqMz0WlUsRf}
pwn.college{ZKqrh6AKCqbUU7WK5.a4wo1SngfmngVMEhP4Mhe7JU00eXA}
pwn.college{SgKJ2S-vwTWrh3PskdWxOc5q7qEK5werHaWJDtTpm93-CT1}
pwn.college{8qsKBDfWx55.RFqwIjxc0oHsysSY8VKu4d0Y1On-7lYVDax}
pwn.college{l0NHsj3DoQs07gEdk3FAmD4CXncf9RCFiKw6Yxut2dmDtYl}
pwn.college{AP49p7N9myF9Ul8493djct.HAy.iQwIogABD7dFIdKCxtyW}
pwn.college{ej-eNdO9mY0EUlH.NuAcyxMu0cDMrMmIaJwKCqWoviR7jWP}
pwn.college{hzwjhbMVdJAG--upRGQKxuVNgjFzV64qK0laeDKHFpUo.DP}
pwn.college{b1wnHZ9fWea8r8mLFCk4r0O.p4lVAgSA83AQ7jLGPIOhYt5}
pwn.college{rCiwoILNEBT8xH1uZRp5EvrnoQFmPXW9Vpt1bmJ8JqS6vwH}
pwn.college{XPxCPwSwsNsvN1TW1ONs39zTJmeA2kDl3iqlUHSIWGDUAo2}
pwn.college{VGHS-oIgruDpKNjZGQWjS4ARWNTdepycl-dBB91cT-CZ6SH}
pwn.college{ORznbOZyEgsmctAxcOizP-5NYpm9OCLYWudxQQl935RzYL-}
pwn.college{daLNPiGGwwfiSHEtYhxVnx36ennGYSgduZuyfT0d5xRNrs9}
pwn.college{5z52eggChuGDIWiBZeflDLgVo9KXV-.-8xwMAT07LjXg5b9}
pwn.college{aQ36IMg68VqxpnJ3t.vPT-ak0VTqTuI1SXvs2YSuWSN7GwG}
pwn.college{vBNSK6ei9VVWXRd3LCViwP3OX67mlnLcOCCxuVPJSL8JbXy}
pwn.college{WAHAhDm5xrY5mFqQ4YaLhmJRwOtzC0ssRHoc8dY7Xed52mK}
pwn.college{mPathTft8cHwXWmJ5VRidXOttXIUdGFMrydN1Do4K6S1GjQ}
pwn.college{q7ba07PrN25rOD4x26Iv7EdQWbwMavguqS-JnG4qEm-izSt}
pwn.college{AwYvVpt4Fogb8mszI6jscdA7wKMToxUGb1ynqIGUy8hCXo1}
pwn.college{y2KsE6KM81sIJHPSGAnYDgH-4iXrBAc6je.y4-O7FKTNf0e}
pwn.college{S7Nhmj9cgnLQwrTOfy487luL6xhLNypAnNDURLA0oh-6Rk7}
pwn.college{nT8axrJ2HqZMaQdw1Z4iuntNoOrlE8NBGM9Zq9ZPBXdsA9E}
pwn.college{0qixVFRcDS9mM24BsrqRVRuiLk-zqyz48Eg6tJL86pVPzEw}
pwn.college{hlsq3T5aRsJcj5LDutMqkguLOI3-mU6eKn5OUZe5PvX7AZs}
pwn.college{q3ENOfEAi5EmBTWkLDr5NTzmtnZoXKrM5abz9s3K.wZv.LJ}
pwn.college{D6RJ7qjcJOAIsa6agFNKA.igpj3PY2t4ccqdB7stniBUcWQ}
pwn.college{hvuz4Gy5VG0r6ZNcH8MbbpT40U273km7PG4gIKQ25Zrfb3x}
pwn.college{EW17AFeixxrh42rx3ZwVINNnEWjlXEUNdfI80Em7knfCzTt}
pwn.college{kAye3N8BQojgDTwdH8.nlIJkB45CLHa4lgrjeZyQrX.2qJA}
pwn.college{r35OY0SJGI1EWfu.feEASHINP.M0S8oOX1HP41QFTnG5FBv}
pwn.college{FNeX4qwxlxwX0Lo1kVQ9gNmzQ8cro3Blo4nW5AbYjiRO2cb}
pwn.college{uDIatdhD3E8BNi-ALj6E3rbTyXC96HHRFHZisOo-rxFvMi3}
pwn.college{zyJ32X-VY9xdTj-7rRyUBhhygI8w86LeqByeCHiTnQ7UvaC}
pwn.college{3SfVgJ-Ps6T-4QW6mOM-E347myGx5ak2K5ZaVdYr6O2mEZx}
pwn.college{xhJZXiPCFJqvt3gc-rscp.-DHrNwHlh31bAiNr5hEh042HC}
pwn.college{v8.i9fI8MJLCk0uIY6MjfC6a550o3JoHBd85-dmat4qvHCP}
pwn.college{wom1uNIXtcst7rNJtLBdOzZvfJqF3uYfav1KkHBA6d3Wuyg}
pwn.college{HLkLOaOavY9GBAASAMdu2PAnLWo1iGapOXQCAajCO39OA-l}
pwn.college{p85n466-FWS3FQ8190a3v7WBgmQw3UQzKL5f7eztx8wPoCA}
pwn.college{8ZzJ.Inao6zdIpiWd9fRVcPy4gz9bV98Ij9o1rdHGkuHQ1r}
pwn.college{27mgPYpXm7opZ4gQ3Y2X.IcEXk9vZXrBLchtuFIBQj7rRTw}
pwn.college{7MVxAy8.px4Ue3Xo6FgzoX7JmFb9WUJBn-bcS-UMCmgQvji}
pwn.college{vzj1V6rsjh8DynxOEvQELWD7IhYn3c4t0Q0Iy3td9InvCJr}
pwn.college{x5-N--FuQgvDGqWeqC4vyZQnHlhFwMTEvF1jNrFrzYhRC5j}
pwn.college{3rE2XoXUKFlNAHdcQH626Lp.dPE-QalgrU7Q9VFTIj6qEy6}
pwn.college{EVznejCxK1VJQ8D5Nj4hhYxhwDq98FHGLTFprVf.Z2x1Vh2}
pwn.college{3eIlLlMCz9AnaA5wLxXPTgp8SgtqfA-UPcX7C.XQWGZx9E3}
pwn.college{ArjynlTRWXg1B7JcOawI5InObUAbobREiKanU.mebIB4DmI}
pwn.college{mDRJNy0BgFBuqVpf9O2rFhTVrf7CNyCEuawE9b1k7Y4Caf9}
pwn.college{prwnYJ16cLzXkL36t.utOeGHD2bERZxoLSkZrMYqLZTBrqp}
pwn.college{b6hIriaHo2dgzgcJttb4L4XqyPVOB1SzoTBPJ239ITE8zmF}
pwn.college{u3aXs4YRs88MWJHD4Vvd-rVcOWIB6a5pCuT5PpNPSJFwOAI}
pwn.college{.6MVP0OS5wbkdKU43IkQ86s9zXl02M94-XVa2laY7AqKL6M}
pwn.college{f3vnxYfRnwz7CPO4vaLJfNM1ZJ8VEMRV.hQGfYGtVAfLV9W}
pwn.college{a8aCZ7pekwG2j2mVO3526t-8.A.uhSqmTf7T4MTOFZsQDwM}
pwn.college{ABJAQNICFwuaK6rpfcJV1BYkZkUipx54s9VmuTWIO02YcMG}
pwn.college{XCG9GqX2jfkFYstQ1pPp3NJBij6DTkeHGTcNUf26D9eHwRp}
pwn.college{fu61C7IPkBJFCAf2NKkdtQjW6ePMGikSd1LQW7MEDwK8YiS}
pwn.college{629LO5XPqT5VyIR0YjAoOEfA3CfPDL.jty4wYTl1Z8wm9hb}
pwn.college{pHkGLgVPYoguwQ5tInXJs1fDSe4AcJpqu2wQz8scXiwMTPK}
pwn.college{VWNv2bC.3DgZzviZOJIKDTV2kxXSDbnBuhSheXuR12yqSdj}
pwn.college{BWhywfGBK-J4E40MnJ1svVz1j3kJ9p0qUtcdT1xwh7OGc6w}
pwn.college{aXSW5J71SEMiQvKoEnzUZg7X-CQ81zHzpd6Blb5boiAJ3Ob}
pwn.college{8UmgDYQjtHeG.MZjeeoXiS2ZA73TTT4w.52wUGa00NjV6cC}
pwn.college{.qwSHO4LZ2VJd7CzakVyQZcXgd8Z4O8WRERo1qRJHQXpFEC}
pwn.college{rImE3ymKLy0i8LRusJXhNJCxyNBBIv4VwMlHD2CnDPZqbM5}
pwn.college{hS3-pxw97cDLw87B5OvlcRvnaGYrLBtGBsayJv9bbiPVGXB}
pwn.college{1yCRI1HqNMKsPgJ2cY3KqA19crXUNJEXgKsoPiy65f7Jsyb}
pwn.college{1S5Lq2FuaVUU6tmUqkbK1LSCmbSOf8g2U3AL1AW6Sk5RAdF}
pwn.college{tWL-o3ByQk2G1ItRJeT0ElAPnsZ53a-Grk30UO524gTudvl}
pwn.college{AZGilzMMAkiRaZprxKO3d.FYuOQtN-m-rIwMAAYAbBbvzbs}
pwn.college{KxrV-1UFMxOepd68nc.-F6cn6EP1ueNMqmizA-JY7X9p1ME}
pwn.college{yHKyj82yckmKQFUAIapT1rfRfOppcfcn7GuxRIxBPT0I7oB}
pwn.college{Gjn6LveN9gk-3GqfjSDEEmaYdybO6-t.3jrQLtyxLj4rTy6}
pwn.college{nGGD5lRi8eN6MlH48hbweUtT4CMI2eq2eVv5Hy7uwtN1A2T}
pwn.college{JIOdSNPZd4bVUred9MhFGEs0Ta-DVB2krUNPojj02TVzln1}
pwn.college{mIFRQgTIIqKbnBQ9TPfbo9cKNZcZr.nopaO8aJi1RtI0m6P}
pwn.college{GlMGHzUhL6Ui2EZdVJDAs-sbbRywFaiOduZ8WIMaDgcbRk6}
pwn.college{316ltL2-43aS2kKDV-CGRDAyV.wF21PvOI9lB.G73HIBl0P}
pwn.college{tsGw0iAlEakU5SLNySF4c1nlAbD0sa40j-eEOs430D1vuqv}
pwn.college{fQWbth4ceqme80p0AeBccTnouWKNglr5x.hYP8pdkObcsdZ}
pwn.college{58JqyKZyfxQ3MQ15ubeDO-5fsa4m7zhwo0BsR0K41hZBvbD}
pwn.college{.pWiNPIpdgdjHipu9jr.1vklNJHm7C-VxUmM5GaoK9PI0Z6}
pwn.college{LwJvj72kNLGoqRjziTY.jcIaFgnR4g6h0h8Y-ZZqYOzoV2h}
pwn.college{NyboAa4csbFIA0VEYWwasUzxZaSm39XjH75majMNrc0a2fZ}
pwn.college{fjVjj4OH359Zv0cdw3SNs5tJRmfJLpQX6oF2U-VzFpN0XSY}
pwn.college{o7Ox.liTSRJ-Ja8jrANt9z7BavUGMogNfQnBJY7U4jzmJKI}
pwn.college{ARZ0scyfy2G1tHb7AkfIDyKMQwGm.T8N7P6eyEJGq12Gus9}
pwn.college{8HQC0NeKrxM4EvD-izj43yuyAkypVk8hgZm5eG9wySLbb0J}
^C
hacker@processes~killing-misbehaving-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 05:12 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6
root           7       1  0 05:12 ?        00:00:00 /run/dojo/bin/sleep 6h
root         137       1  0 05:12 ?        00:00:00 /bin/bash /challenge/.init
root         138       1  0 05:12 ?        00:00:00 /bin/bash /challenge/.init
root         140     137  0 05:12 ?        00:00:00 sleep 6h
root         141     138  0 05:12 ?        00:00:00 sleep 6h
hacker       153       1  0 05:12 ?        00:00:00 /nix/store/g0q8n7xfjp7znj41hcgrq893a9m0i474-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0
hacker       157     153  0 05:12 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       174     157  0 05:15 pts/0    00:00:00 ps -ef
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{wU1074mDVcUZeOmgdqt1nGLDHK4.0FNzMDOxwyM0AzNzEzW}
```
## What I learned
To kill misbehaving processes.

### Challenge 5:
  **Flag**  pwn.college{sQnyUBL443FloX03-SQnQQ-fCOO.QX1QDO0wyM0AzNzEzW}
  
Here we are using the Ctrl + Z to suspend the process run to the background and then running it again to get the fLag.
 ``` 
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         162     152  0 05:20 pts/0    00:00:00 bash /challenge/run
root         164     162  0 05:20 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!

hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         169     152  0 05:20 pts/0    00:00:00 bash /challenge/run
root         171     169  0 05:20 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         169     152  0 05:20 pts/0    00:00:00 bash /challenge/run
root         176     152  0 05:21 pts/0    00:00:00 bash /challenge/run
root         178     176  0 05:21 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{sQnyUBL443FloX03-SQnQQ-fCOO.QX1QDO0wyM0AzNzEzW}
hacker@processes~suspending-processes:~$
```
## What I learned
To suspend processes to the background.

### Challenge 6:
  **Flag**  pwn.college{ItqoASqCe5UqhQvDMYFty8NU6lv.QX4EDO0wyM0AzNzEzW}
 Here we are using the Ctrl + Z to suspend the run program and then using the fg command to resume it and bring it back to the foreground.
 ``` 
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg /challenge/run
/challenge/run
I'm back! Here's your flag:
pwn.college{QbZ2jAw-cQcsIAWwv4w1d_PLtFG.QX2QDO0wyM0AzNzEzW}
Don't forget to press Enter to quit me!

Goodbye!
hacker@processes~resuming-processes:~$ 
```
## What I learned
To use the fg command to bring back a suspended program.

### Challenge 7:
  **Flag**  pwn.college{Uq35P1QaVGwpL98XvY6WX7V5kE_.QX3QDO0wyM0AzNzEzW}
Here we are running the run program, then we are suspending it and then running it again in the background using the bg command.
 ``` 
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         146 S+   bash /challenge/run
root         148 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         153 S+   bash /challenge/run
root         155 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         153 S    bash /challenge/run
root         163 S    sleep 6h
root         164 S+   bash /challenge/run
root         166 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{Uq35P1QaVGwpL98XvY6WX7V5kE_.QX3QDO0wyM0AzNzEzW}
hacker@processes~backgrounding-processes:~$ 
```
## What I learned
The use of the bg command.

### Challenge 8:
  **Flag**  pwn.college{U9CRfn6eTgaeX_ynWl7pbCtBmt8.QX4QDO0wyM0AzNzEzW}
Here we are first running the run program, then we are suspending it and then we are again resuming it, first in the backgorund and then bringing it into the foreground.
 ``` 
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg /challenge/run
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.

hacker@processes~foregrounding-processes:~$ fg /challenge/run
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{U9CRfn6eTgaeX_ynWl7pbCtBmt8.QX4QDO0wyM0AzNzEzW}
hacker@processes~foregrounding-processes:~$ 
```
## What I learned
Foregrounding a backgrounded process.

### Challenge 9:
  **Flag**  pwn.college{sdBvzmQiaybuuH9CYVHYYyDEAEb.QX5QDO0wyM0AzNzEzW}
  Here we are runing the run program directly in the background using the & attriubute.
 ``` 
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 145
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{sdBvzmQiaybuuH9CYVHYYyDEAEb.QX5QDO0wyM0AzNzEzW}

[1]+  Done                    /challenge/run
hacker@processes~starting-backgrounded-processes:~$ 
```
## What I learned
To run a program in the background.

### Challenge 10:
  **Flag**  pwn.college{kEG2XehMtR2m9Y60tu923Ew-Hh9.QX5YDO1wyM0AzNzEzW}
Here we are using the ? variable to access the error code of the get-code program and then using it as the argument for the submit-code program.
 ``` 
hacker@processes~process-exit-codes:~$ touch /challenge/get-code
touch: cannot touch '/challenge/get-code': Permission denied
hacker@processes~process-exit-codes:~$ echo $?
1
hacker@processes~process-exit-codes:~$ /challenge/submit-code 1
/challenge/submit-code: line 3: /tmp/.code: No such file or directory
Incorrect... Make sure to use $? immediately after running /challenge/get-code. 
Your shell will overwrite the $? variable with the exit value of any other 
command you run!
hacker@processes~process-exit-codes:~$ /chall3enge/get-code
bash: /chall3enge/get-code: No such file or directory
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
161
hacker@processes~process-exit-codes:~$ /challenge/submit-code 161
CORRECT! Here is your flag:
pwn.college{kEG2XehMtR2m9Y60tu923Ew-Hh9.QX5YDO1wyM0AzNzEzW}
hacker@processes~process-exit-codes:~$ 
```
## What I learned
To find the exit code of the last program.

## References
None
