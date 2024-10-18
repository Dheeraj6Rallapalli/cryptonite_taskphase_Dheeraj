# Perceiving Permissions
## Changing file ownership
>[!TIP]
>We use `chown` command to change ownership of a file by passing new owner name and file name as arguments

here to aquire flag we need to change ownership of `/flag` file to hacker using `$ chown hacker /flag` commnad and then we need to read the file using `$ cat /flag` command to get the flag
```
hacker@permissions~changing-file-ownership:~$ ls -l
total 36
-rw-r--r-- 1 hacker hacker    4 Oct 10 15:49 COLLEGE
drwxr-xr-x 2 hacker hacker 4096 Oct  1 17:09 Desktop
-rw-r--r-- 1 hacker hacker    8 Oct 10 16:31 PWN
-rw-r--r-- 1 hacker hacker    0 Oct  5 18:50 college
-rw-r--r-- 1 root   hacker   58 Oct  2 19:48 d
-rw-r--r-- 1 hacker hacker  829 Oct 10 16:16 instructions
drwxr-xr-x 2 hacker hacker 4096 Oct  1 18:40 leap
-rw-r--r-- 1 hacker hacker   93 Oct 10 16:16 myflag
lrwxrwxrwx 1 hacker hacker    5 Oct  6 21:05 not-the-flag -> /flag
-rw-r--r-- 1 root   hacker   77 Oct 10 17:49 output.txt
-rw-r--r-- 1 hacker hacker  435 Oct 10 16:06 the-flag
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{giPVFKt6PlI7WatMBByky3uAIZ5.dFTM2QDL1MzN0czW}
```
>Flag: pwn.college{giPVFKt6PlI7WatMBByky3uAIZ5.dFTM2QDL1MzN0czW}

## Groups and Files
>[!TIP]
>We use `chgrp` command to change the group of a file by giving new group name and file name as arguments

here to aquire flag we need to change the group of `/flag` file to `hacker` using `$ chgrp hacker /flag` command and then we need to read it using `$ cat /flag` command to get the flag
```
hacker@permissions~groups-and-files:~$ ls -l
total 36
-rw-r--r-- 1 hacker hacker    4 Oct 10 15:49 COLLEGE
drwxr-xr-x 2 hacker hacker 4096 Oct  1 17:09 Desktop
-rw-r--r-- 1 hacker hacker    8 Oct 10 16:31 PWN
-rw-r--r-- 1 hacker hacker    0 Oct  5 18:50 college
-rw-r--r-- 1 root   hacker   58 Oct  2 19:48 d
-rw-r--r-- 1 hacker hacker  829 Oct 10 16:16 instructions
drwxr-xr-x 2 hacker hacker 4096 Oct  1 18:40 leap
-rw-r--r-- 1 hacker hacker   93 Oct 10 16:16 myflag
lrwxrwxrwx 1 hacker hacker    5 Oct  6 21:05 not-the-flag -> /flag
-rw-r--r-- 1 root   hacker   77 Oct 10 17:49 output.txt
-rw-r--r-- 1 hacker hacker  435 Oct 10 16:06 the-flag
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{s-Q5v5_jcax9mRYKpDtLNpLTljz.dFzNyUDL1MzN0czW}
```
>Flag: pwn.college{s-Q5v5_jcax9mRYKpDtLNpLTljz.dFzNyUDL1MzN0czW}

## Fun with Groups names
>[!TIP]
>We use `id` command to know the groups which we are present in

Here to aquire flag we need to find the groups which we are in using `$ id` command and find the groups other than `hacker` and we need to change the `/flag` file to that group
using `$ chgrp grp4975 /flag` command and then we need to read the file using `$ cat /flag` command to get the flag
```
hacker@permissions~fun-with-groups-names:~$ ls -l
total 36
-rw-r--r-- 1 hacker grp4975    4 Oct 10 15:49 COLLEGE
drwxr-xr-x 2 hacker grp4975 4096 Oct  1 17:09 Desktop
-rw-r--r-- 1 hacker grp4975    8 Oct 10 16:31 PWN
-rw-r--r-- 1 hacker grp4975    0 Oct  5 18:50 college
-rw-r--r-- 1 root   grp4975   58 Oct  2 19:48 d
-rw-r--r-- 1 hacker grp4975  829 Oct 10 16:16 instructions
drwxr-xr-x 2 hacker grp4975 4096 Oct  1 18:40 leap
-rw-r--r-- 1 hacker grp4975   93 Oct 10 16:16 myflag
lrwxrwxrwx 1 hacker grp4975    5 Oct  6 21:05 not-the-flag -> /flag
-rw-r--r-- 1 root   grp4975   77 Oct 10 17:49 output.txt
-rw-r--r-- 1 hacker grp4975  435 Oct 10 16:06 the-flag
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp4975) groups=1000(grp4975)
hacker@permissions~fun-with-groups-names:~$ chgrp grp4975 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{IX9-qkCyOddJYdD8VckJErnTCch.dJzNyUDL1MzN0czW}
```
>Flag: pwn.college{IX9-qkCyOddJYdD8VckJErnTCch.dJzNyUDL1MzN0czW}

## Changing permissions
- **File Permissions**:
  - `r`: Read permission.
  - `w`: Write permission.
  - `x`: Execute permission.
  - `-`: No permission.
  
- **chmod**: Changes file permissions using this `WHO+/-WHAT` format, where `WHO` can be:
  - `u` for the file owner (user).
  - `g` for the group.
  - `o` for others (all users not in the group or the owner).
  - `a` for all (user, group, and others).

- **Permission Modifications**:
  - `o+r`: Adds read permission for others.
  - `o-w`: Removes write permission for others (if present).

here to aquire flag we need to change the mode of `/flag` file so that others can read it, for this we use `$ chmod o+r /flag` commnad and then we use `$ cat /flag` command to read the file and to get the flag
```
hacker@permissions~changing-permissions:~$ ls -l
total 36
-rw-r--r-- 1 hacker hacker    4 Oct 10 15:49 COLLEGE
drwxr-xr-x 2 hacker hacker 4096 Oct  1 17:09 Desktop
-rw-r--r-- 1 hacker hacker    8 Oct 10 16:31 PWN
-rw-r--r-- 1 hacker hacker    0 Oct  5 18:50 college
-rw-r--r-- 1 root   hacker   58 Oct  2 19:48 d
-rw-r--r-- 1 hacker hacker  829 Oct 10 16:16 instructions
drwxr-xr-x 2 hacker hacker 4096 Oct  1 18:40 leap
-rw-r--r-- 1 hacker hacker   93 Oct 10 16:16 myflag
lrwxrwxrwx 1 hacker hacker    5 Oct  6 21:05 not-the-flag -> /flag
-rw-r--r-- 1 root   hacker   77 Oct 10 17:49 output.txt
-rw-r--r-- 1 hacker hacker  435 Oct 10 16:06 the-flag
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{gSAv7Vp40JtHzbiqkrsPei-vKrr.dNzNyUDL1MzN0czW}
```
>Flag: pwn.college{gSAv7Vp40JtHzbiqkrsPei-vKrr.dNzNyUDL1MzN0czW}

## Executable files
here to aquire flag  we need to make `/challenge/run`  executable using `$ chmod u+x /challenge/run` command and then we need to run `$ /challenge/run` program to get the flag 
```
hacker@permissions~executable-files:~$ chmod u+x /challenge/run 
hacker@permissions~executable-files:~$ /challenge/run 
Successful execution! Here is your flag:
pwn.college{sn8_yU8FYqc35rd4VLoH7NbxKtt.dJTM2QDL1MzN0czW}
```
>Flag: pwn.college{sn8_yU8FYqc35rd4VLoH7NbxKtt.dJTM2QDL1MzN0czW}

## Permission tweaking process
Here to aquire flag we need to run `$ /challenge/run` commnad and then we need to follow the given instructions so that we will get our flag
```
hacker@permissions~permission-tweaking-practice:~$ /challenge/run 
Round 0 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw----r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-r /challenge/pwn
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": rw----r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwx---r-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+x,o+x /challenge/pwn
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": rwx---r-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwx---r--
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-x /challenge/pwn
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": rwx---r--
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwxr-xr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+r,g+x,o+x /challenge/pwn
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": rwxr-xr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwx------
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-r,g-x,o-r,o-x /challenge/pwn
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": rwx------
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwxr-x---
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+r,g+x /challenge/pwn
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": rwxr-x---
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwx--x---
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-r /challenge/pwn
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": rwx--x---
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwxr-xr--
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+r,o+r /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{QGvrchS0g0_kRlGBsBziPPQ5k82.dBTM2QDL1MzN0czW}
```
>Flag: pwn.college{QGvrchS0g0_kRlGBsBziPPQ5k82.dBTM2QDL1MzN0czW}

## Permissions setting Process
>[!TIP]
>We can also use `=` to assign permissions
here to aquire flag we need to run `$ /challenge/run` commnad and then follow the given instructions to get the flag
```
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 0 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwxr---wx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=r,o=wx /challenge/pwn
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": rwxr---wx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwx-w--w-
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=w,o=w /challenge/pwn
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": rwx-w--w-
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r---wxr--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=wx,o=r /challenge/pwn
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": r---wxr--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r-xrw---x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rx,g=rw,o=x /challenge/pwn
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": r-xrw---x
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ---r-xrw-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=-,g=rx,o=rw /challenge/pwn
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": ---r-xrw-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwxr--rwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=r,o=rwx /challenge/pwn
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": rwxr--rwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -w--wx---
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=wx,o=- /challenge/pwn
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": -w--wx---
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w--wx-w-
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod o=w /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{MkkAaDJpjbHVVQsTdryyMqWdvtz.dNTM5QDL1MzN0czW}
```
>Flag: pwn.college{MkkAaDJpjbHVVQsTdryyMqWdvtz.dNTM5QDL1MzN0czW}

## The SUID bit
>[!TIP]
>There are many cases in which non-root users need elevated access to do certain system tasks. The system admin can't be there to give them the password every time a user wanted to do a task that only root/sudoers can do. The "Set User ID" (SUID) permissions bit allows the user to run a program as the owner of that program's file and we can do this using `chmod u+s [program]` commnad

here to aquire flag we need to SUID the `/challenge/getroot` file to the user and then we will get the access to shell then we need to check the files init using `ls` command and then we need to read the files then we will get to know that flag is in `not-the-flag`
```
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot 
hacker@permissions~the-suid-bit:~$ /challenge/getroot 
SUCCESS! You have set the suid bit on this program, and it is running as root! 
Here is your shell...
root@permissions~the-suid-bit:~# ls
COLLEGE  PWN      d             leap    not-the-flag  the-flag
Desktop  college  instructions  myflag  output.txt
root@permissions~the-suid-bit:~# cat the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{4SgqJFj2_uSBUT3aNsrhumZwyL8.ddDM5QDL1MzN0czW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
root@permissions~the-suid-bit:~# cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{olEGavEdXt93FFL-7vXfFi9RRhE.ddjN1QDL1MzN0czW}

root@permissions~the-suid-bit:~# cat not-the-flag
pwn.college{MXVDbGRxexpsAIpW1eTNMJXXfyF.dNTM2QDL1MzN0czW}
```
>Flag: pwn.college{MXVDbGRxexpsAIpW1eTNMJXXfyF.dNTM2QDL1MzN0czW}
