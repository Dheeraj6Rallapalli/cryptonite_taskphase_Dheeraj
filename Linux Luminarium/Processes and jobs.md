# Processes and jobs

## Listing Processes
>[!TIP]
>`ps` either stands for "process snapshot" or "process status", and it lists processes. By default, ps just lists the processes running in your terminal
>you can use `-e` to list "every" process and `-f` for a "full format" output, including arguments. These can be combined into a single argument `-ef`.
>you can use `a` to list processes for all users, `x` to list processes that aren't running in a terminal, and `u` for a "user-readable" output. These can be combined into a single argument `aux`.

here to aquire flag we need to list the current running process and find the renamed name of `/challenge/run` using `$ ps -ef` command . By this we will know that `/challenge/11666-run-26230` this is the new file name and to get the flag we will run `$ /challenge/11666-run-26230` command
```
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 15:53 ?        00:00:00 /sbin/docker-init -- /nix/va
root           7       1  0 15:53 ?        00:00:00 /run/dojo/bin/sleep 6h
root          68       1  0 15:53 ?        00:00:00 /challenge/11666-run-26230
root          72      68  0 15:53 ?        00:00:00 sleep 6h
hacker        73       0  0 15:53 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker        90      73  0 15:53 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:~$ /challenge/11666-run-26230
Yahaha, you found me! Here is your flag:
pwn.college{wwurxRPaLMp6yy-dV757dPPdCRL.dhzM4QDL1MzN0czW}
Now I will sleep for a while (so that you could find me with 'ps').
```
>Flag: pwn.college{wwurxRPaLMp6yy-dV757dPPdCRL.dhzM4QDL1MzN0czW}

## Killing processes
>[!TIP]
>`kill` command will terminate a process in a way that gives it a chance to get its affairs in order before ceasing to exist.

here to aquire flag we need to find the `dont_run` process as given, for this we use `$ ps -e` command then we will get list of processes init the one with `sleep` is the process we are searching for and the PID number is 74 and we need to terminate it, for this we use `$ kill 74` command and then we will run `$ /challenge/run` command to get the flag
```
hacker@processes~killing-processes:~$ ps -e
    PID TTY          TIME CMD
      1 ?        00:00:00 docker-init
      7 ?        00:00:00 /run/dojo/bin/s
     71 ?        00:00:00 su
     73 ?        00:00:00 bash
     74 ?        00:00:00 sleep
     75 pts/0    00:00:00 ssh-entrypoint
     92 pts/0    00:00:00 ps
hacker@processes~killing-processes:~$ kill 74
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{0piFDc2LrpfmQON9_aWdFe55jP5.dJDN4QDL1MzN0czW}
```
>Flag: pwn.college{0piFDc2LrpfmQON9_aWdFe55jP5.dJDN4QDL1MzN0czW}

## Interrrupting the processes
>[!TIP]
>we use `Ctrl-C` key to interrupt and exit a running process

here to aquire flag we need to interrupt the process `/challenge/run` by running it using `$ /challenge/run` command and then we need to interrupt it using `Ctrl-C` key to get the flag
```
hacker@processes~interrupting-processes:~$ /challenge/run 
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{kp5-pSBzB9I1vUpAeDtV8t1YzIi.dNDN4QDL1MzN0czW}
```
>Flag: pwn.college{kp5-pSBzB9I1vUpAeDtV8t1YzIi.dNDN4QDL1MzN0czW}

## Suspending processes
>[!TIP]
>we use `Ctrl-Z` key to suspend a running process

here to aquire flag we need to suspend the process `/challenge/run` by running it using `$ /challenge/run` command and then we need to suspend it using `Ctrl-Z` key and the we need to run this `$ /challenge/run` command again to get the flag
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 18:53 pts/0    00:00:00 bash /challenge/run
root          84      82  0 18:53 pts/0    00:00:00 ps -f

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
root          82      65  0 18:53 pts/0    00:00:00 bash /challenge/run
root          89      65  0 18:53 pts/0    00:00:00 bash /challenge/run
root          91      89  0 18:53 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{0S7x15hA9_GnLnuhPZ1hHiTPjUS.dVDN4QDL1MzN0czW}
```
>Flag: pwn.college{0S7x15hA9_GnLnuhPZ1hHiTPjUS.dVDN4QDL1MzN0czW}

## Resuming processes
>[!TIP]
>we use `fg` command to resume a suspended process in foreground

here to aquire flag we need to suspend the process `/challenge/run` by running it using `$ /challenge/run` command and then we need to suspend it using `Ctrl-Z` key and the we need to resume it using `$ fg` command to get the flag
```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{MpwwuJJZvMV15O-9iVQH_PiaoyX.dZDN4QDL1MzN0czW}
Don't forget to press Enter to quit me!

Goodbye!
```
>Flag: pwn.college{MpwwuJJZvMV15O-9iVQH_PiaoyX.dZDN4QDL1MzN0czW}

## Backgrounding processes
>[!TIP]
>we use `bg` command to resume a suspended process in background

here to aquire flag we need to suspend the process `/challenge/run` by running it using `$ /challenge/run` command and then we need to suspend it using `Ctrl-Z` key and the we need to resume it in background using `$ bg` command and then we need to run another copy of `$ /challenge/run` command to get the flag 
```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S+   bash /challenge/run
root          84 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S    bash /challenge/run
root          92 S    sleep 6h
root          93 S+   bash /challenge/run
root          95 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{kYVbTqugRHx14GVrJYbjPr_YVa7.ddDN4QDL1MzN0czW}
```
>Flag: pwn.college{kYVbTqugRHx14GVrJYbjPr_YVa7.ddDN4QDL1MzN0czW}

## Foregrounding processes
here to aquire flag we need to suspend the process `/challenge/run` by running it using `$ /challenge/run` command and then we need to suspend it using `Ctrl-Z` key and the we need to resume it in background using `$ bg` command and then we need to run the process in the foreground for that we use `$ fg` command so we will get our flag
```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{saVNkQTdkv8qTU1JG1D5Tl0x7cD.dhDN4QDL1MzN0czW}
```
>Flag: pwn.college{saVNkQTdkv8qTU1JG1D5Tl0x7cD.dhDN4QDL1MzN0czW}

## Starting backgrounded processes
>[!TIP]
>To run a process in the background directly we need append `&` to the file

here to aquire flag we need to run `/challenge/run` file in background, for that we use `$ /challenge/run &` commnad
```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 82
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{IHdciV7k90qq_wKxgDx3aML3SEL.dlDN4QDL1MzN0czW}
```
>Flag: pwn.college{IHdciV7k90qq_wKxgDx3aML3SEL.dlDN4QDL1MzN0czW}

## Process exit codes
>[!TIP]
>we use `echo $?` command to see the exit codes of the error programs

here to aquire flag we need run `$ /challenge/get-code` command which will exit without running and then we need to find the exit code using `$ echo $?` commnad which is an argument to `/challenge/submit-code` command which gives us flag when we run it as `$ /challenge/submit-code 65` command 
```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
65
hacker@processes~process-exit-codes:~$ /challenge/submit-code 65
CORRECT! Here is your flag:
pwn.college{Q_MnD2x_GVk3hQn0gYSgRDqNAly.dljN4UDL1MzN0czW}
```
>Flag: pwn.college{Q_MnD2x_GVk3hQn0gYSgRDqNAly.dljN4UDL1MzN0czW}
