# Practicing piping
>Standard Input is the channel through which the process takes input. For example, your shell uses Standard Input to read the commands that you input.

>Standard Output is the channel through which processes output normal data, such as the flag when it is printed to you in previous challenges or the output of utilities such as ls.

>Standard Error is the channel through which processes output error details. For example, if you mistype a command, the shell will output, over standard error, that this command does not exist.

## Redirecting output
here to aquire flag we need to overwrite `PWN` to `COLLEGE` so that when we read `COLLEGE` file it will dispaly `PWN` we can achieve this by following process and we use `$ echo PWN > COLLEGE` command
```
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{IWcq7-nprHwdK4H_Sp-KqV5TK_w.dRjN1QDL1MzN0czW}
```
>Flag: pwn.college{IWcq7-nprHwdK4H_Sp-KqV5TK_w.dRjN1QDL1MzN0czW}

## Redirecting more output
here to aquire flag we need to overwrite `myflag` file with `/challenge/run` and then we need to read `myflag` file so that we will get our flag, for this we will use `$ /challenge/run > myflag` command
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
[FLAG] pwn.college{Abh129LqIPdhMQDvVKizNl2rSbI.dVjN1QDL1MzN0czW}
```
>Flag: pwn.college{Abh129LqIPdhMQDvVKizNl2rSbI.dVjN1QDL1MzN0czW}

## Appending output
here to aquire flag we need to append `/challenge/run` this file to this `/home/hacker/the-flag` and then we need to read the `/home/hacker/the-flag` file to get the flag, for this we will use `$ /challenge/run >> /home/hacker/the-flag` command
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
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
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
```
>Flag: pwn.college{4SgqJFj2_uSBUT3aNsrhumZwyL8.ddDM5QDL1MzN0czW}

## Redirecting errors
here to aquire flag we need to redirect file `/challenge/run` output to `myflag` and errors to `instructions` after that by reading file `myflag` we will get our flag and by reading `instructions` file we will get instructions, for this we will use `$ /challenge/run > myflag 2> instructions` command
```
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{olEGavEdXt93FFL-7vXfFi9RRhE.ddjN1QDL1MzN0czW}

hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
```
>Flag: pwn.college{olEGavEdXt93FFL-7vXfFi9RRhE.ddjN1QDL1MzN0czW}

## Redirecting input
here to aquire flag we need to redirect value `COLLEGE` to `PWN` file by using `$ echo COLLEGE > PWN` and then we need to redirect the output of `PWN` as input to `/challenge/run` by using `$ /challenge/run < PWN` command so that we will get our flag
```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{Yxe0aioB1MjX_CseBiQAoSqG8mV.dBzN1QDL1MzN0czW}
```
>Flag: pwn.college{Yxe0aioB1MjX_CseBiQAoSqG8mV.dBzN1QDL1MzN0czW}

## Grepping stored results
here to aquire flag we need to truncate the output from `/challenge/run` to `/tmp/data.txt` by using `$ /challenge/run > /tmp/data.txt` command and then we need to grep the flag from `/tmp/data.txt` to get the flag, for this we use `$ grep pwn.college /tmp/data.txt
` command
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
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{0MRRK2p31uz60pgqs8iGqZLxgSl.dhTM4QDL1MzN0czW}
```
>Flag: pwn.college{0MRRK2p31uz60pgqs8iGqZLxgSl.dhTM4QDL1MzN0czW}

## Grepping live output
>[!TIP]
>![image](https://github.com/user-attachments/assets/5c2881c2-8dc1-4d9d-afc0-ab75de516127)

here to aquire flag we need to grep for the flag in `/challenge/run` for that we use `$ /challenge/run | grep pwn.college` 
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{gmiAFmQURnt4LcfRzAi1vMFrSsx.dlTM4QDL1MzN0czW}
```
>Flag: pwn.college{gmiAFmQURnt4LcfRzAi1vMFrSsx.dlTM4QDL1MzN0czW}

## Grepping errors
here to aquire flag we need to need to grep error of `/challenge/run` as output to get the flag, for this we use `$ /challenge/run 2>& 1 | grep pwn.college` command, here `2>& 1` will help to redirect error as output
```
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{8kxznYcr2GqiipIzdzKn2AjrEcS.dVDM5QDL1MzN0czW}
```
>Flag: pwn.college{8kxznYcr2GqiipIzdzKn2AjrEcS.dVDM5QDL1MzN0czW}

## Duplicating piped data with tee
>[!TIP]
>The tee command, named after a "T-splitter" from plumbing pipes, duplicates data flowing through your pipes to any number of files provided on the command line. For example:
>![image](https://github.com/user-attachments/assets/c4781079-e278-462f-bbc8-8fe7aaeaae5f)

here to aquire flag we need to we need to run `$ /challenge/pwn |/challenge/college` but as mentioned we need to give an argument to `/challenge/pwn` in order to get the flag so we will use tee command to find the argument by using `$ /challenge/pwn | tee output.txt |/challenge/college` so that the data from `/challenge/pwn` is copied to `output.txt` from there by reading it we will know about the argument and then by running `$ /challenge/pwn --secret "QBwouTKS" |/challenge/college` command we will get the flag
```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee output.txt |/challenge/college 
Processing...
WARNING: you are overwriting file output.txt with tee's output...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat output.txt
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "QBwouTKS"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret [QBwouTKS] |/challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret "QBwouTKS" |/challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{QBwouTKSsD52uExnnBrE8zcTNNv.dFjM5QDL1MzN0czW}
```
>Flag: pwn.college{QBwouTKSsD52uExnnBrE8zcTNNv.dFjM5QDL1MzN0czW}

## Writing to multiple programs
here to aquire flag we need to run `/challenge/hack` program along with it we need to duplicate the output of `/challenge/hack` as input to `/challenge/the` and `/challenge/planet`, for this we will use `$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)` command to get the flag
```
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
18274933808020839
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{UrC8AU1Eh28xH6s5c4lCxkAQ6Qp.dBDO0UDL1MzN0czW}
```
>Flag: pwn.college{UrC8AU1Eh28xH6s5c4lCxkAQ6Qp.dBDO0UDL1MzN0czW}

## Split piping stderr and stdout
here to aquire flag we need to redirect `/challenge/hack` file's error to `/challenge/the` and output to `/challenge/planet` for this we use `$ /challenge/hack 2> >(/challenge/the) > >(/challenge/planet)` command to get the flag
```
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) > >(/challenge/planet)
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{MaF5Jfpjtke-lzLNx6YDuiTxbuj.dFDNwYDL1MzN0czW}
```
>Flag: pwn.college{MaF5Jfpjtke-lzLNx6YDuiTxbuj.dFDNwYDL1MzN0czW}
