# File Globbing
Globbing let's you know the files with out their full name or path by just giving the reference
## Matching with *
>[!TIP]
>When it encounters a * character in any argument, the shell will treat it as "wildcard" and try to replace that argument with any files that match the pattern. It's easier to show you than explain:

>![image](https://github.com/user-attachments/assets/fe915795-d929-487d-ac27-e2f5a9516cd3)

here to aquire flag we need to enter into the directory by passing at most four characters so we use file globbing to pass argument as `$ cd /ch*` and then we use `$ /challenge/run` to get the flag
```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{0iCV_cbJaVimrljRfmRLu0nuOAF.dFjM4QDL1MzN0czW}
```
>Flag: pwn.college{0iCV_cbJaVimrljRfmRLu0nuOAF.dFjM4QDL1MzN0czW}

## Matching with ?
>[!TIP]
>When it encounters a ? character in any argument, the shell will treat it as single-character wildcard. This works like *, but only matches one character
>![image](https://github.com/user-attachments/assets/bbe5ab09-59c1-4631-b2db-8c59938ee3c1)

here to aquire the flag we need to enter into the directory without using 'c' and 'l'
so we use `?` which replace them as `$ cd /?ha??enge` and then to get the flag we use `/challenge$ /challenge/run` command 
```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{g94G7E63eYcdtwpIpsX5Rx3sY62.dJjM4QDL1MzN0czW}
```
>Flag: pwn.college{g94G7E63eYcdtwpIpsX5Rx3sY62.dJjM4QDL1MzN0czW}

## Matching with []
>[!TIP]
>The square brackes are, essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets. For example, [pwn] will match the character p, w, or n. For example:
>![image](https://github.com/user-attachments/assets/839eff16-f236-4ae2-8877-0e2da6902a27)

here to aquire flag we need to enter into a directory as given by using `$ cd /challenge/files`
and then we need to give four files as single argument to `/challenge/run` as given in the instructions by using `$ /challenge/run file_[bash]` to get the flag
```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{0RXw1rjV9IOXQfP7ELPznyYr_eZ.dNjM4QDL1MzN0czW}
```
>Flag: pwn.college{0RXw1rjV9IOXQfP7ELPznyYr_eZ.dNjM4QDL1MzN0czW}

## Matching paths with []
>[!TIP]
>example for expanding path with globbed argument
>![image](https://github.com/user-attachments/assets/26bbe87e-a15c-4419-95a6-97f147def61d)

here to aquire flag we need to run the command by passing path with globbing as `$ /challenge/run /challenge/files/file_[bash]`
command
```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{wYUiLI8j4iAAFLv1vxnnyU3GzTo.dRjM4QDL1MzN0czW}
```
>Flag: pwn.college{wYUiLI8j4iAAFLv1vxnnyU3GzTo.dRjM4QDL1MzN0czW}

## Mixing globs
here to aquire flag we need to enter into directory as given by `$ cd /challenge/files` and then we need to pass the arguments "challenging", "educational", and "pwning" to with atmost 6 characters to `/challenge/run` to get the flag.
 So we use `$ /challenge/run [cep]*` which matches all the files so we will get the flag
 ```
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{MA22gFIrIbgFHx_0F1cVnujBou6.dVjM4QDL1MzN0czW}
```
>Flag: pwn.college{MA22gFIrIbgFHx_0F1cVnujBou6.dVjM4QDL1MzN0czW}

## Exclusionary globbing
>[!TIP]
>to filter out files in a glob! Luckily, [] helps you do just this. If the first character in the brackets is a ! or (in newer versions of bash) a ^, the glob inverts, and that bracket instance matches characters that aren't listed. For example:
>![image](https://github.com/user-attachments/assets/697e7f2c-b46a-447e-9804-b140ded0b788)
>NOTE: The ! character has a different special meaning in bash when it's not the first character of a [] glob, so keep that in mind if things stop making sense! ^ does not have this problem, but is also not compatible with older shells.

here to aquire flag we need to enter into directory as given in instructios by `$ cd /challenge/files` and then we need to run the files that doesn't start with p,w or n so we use `$ /challenge/run [^pwn]*` command to get the flag
```
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]*
You got it! Here is your flag!
pwn.college{4vxnBt0VGGb8M-7nhhITFkFgW3W.dZjM4QDL1MzN0czW}
```
>Flag: pwn.college{4vxnBt0VGGb8M-7nhhITFkFgW3W.dZjM4QDL1MzN0czW}
