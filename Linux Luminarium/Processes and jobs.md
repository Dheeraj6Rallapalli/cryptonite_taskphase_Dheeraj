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
