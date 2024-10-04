# Comprehending Commands
## cat: not the pet, but the command!
Type `$ cat flag` to get the flag
>[!TIP]
>we use `cat` to read or concatenate files as arguments
```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{4n0yZJZiNK9e6Y3DM5TzXigeubc.dFzN1QDL1MzN0czW}
```
>Flag: pwn.college{4n0yZJZiNK9e6Y3DM5TzXigeubc.dFzN1QDL1MzN0czW}

## Catting absolute paths
Type `$ cat /flag` to get the flag

here we followed absolute path to read the flag
```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{kST2vOoQ3DpPwBzqKE5tpm2zgrf.dlTM5QDL1MzN0czW}
```
>Flag: pwn.college{kST2vOoQ3DpPwBzqKE5tpm2zgrf.dlTM5QDL1MzN0czW}

## More catting practice 
Type `$ cat /usr/libx32/gconv/flag` to get the flag

the absolute path to read the file is: `/usr/libx32/gconv/flag`
```
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /usr/libx32/gconv/flag. Go cat it out **without** cding into that 
directory!
hacker@commands~more-catting-practice:~$ cat /usr/libx32/gconv/flag
pwn.college{wOdbVYO0sdxxLJZ252GvnCexghu.dBjM5QDL1MzN0czW}
```
>Flag: pwn.college{wOdbVYO0sdxxLJZ252GvnCexghu.dBjM5QDL1MzN0czW}

## Grepping for a needle in haystack
>[!TIP]
>we use `grep` command which will search for the file by taking lines in the file as arguments and we use it for big files.
Type `$ grep pwn.college /challenge/data.txt` to get the flag

here we used `grep` which will search for the file by taking lines in the file as arguments like `pwn.college` in this code
and we use it for big files.
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{AObBC0uFBxZ5WqI5QI20scVqZB3.ddTM4QDL1MzN0czW}
```
>Flag: pwn.college{AObBC0uFBxZ5WqI5QI20scVqZB3.ddTM4QDL1MzN0czW}

## Listing files
>[!TIP]
>we use `ls` command with this command we see all the files present in the current directory

with `ls` command we saw the files in `/challenge` and we found two files they are:
```
2941-renamed-run-22793  DESCRIPTION.md
```
Then we use `$ /challenge/2941-renamed-run-22793` command to get the flag because we got the renamed file
```
hacker@commands~listing-files:~$ ls /challenge
2941-renamed-run-22793  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/2941-renamed-run-22793
Yahaha, you found me! Here is your flag:
pwn.college{kxUYYYYhAiXS7if_hnY7EQqL-4Y.dhjM4QDL1MzN0czW}
```
>Flag: pwn.college{kxUYYYYhAiXS7if_hnY7EQqL-4Y.dhjM4QDL1MzN0czW}

## Touching files
>[!TIP]
>we use `touch` command to create blank files and giving path and file name as argument

with `touch` command we created two file named `pwn` and `college` in `/tmp`
```
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
```
then we use `$ cd /tmp` to enter in to the directory

then to aquire flag we use `$ /challenge/run` as command
```
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ ls
bin  college  hsperfdata_root  pwn  tmp.XvrUsDZh8M
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{omhpUARytWmSrjUhVr4mOerpjaC.dBzM4QDL1MzN0czW}
```
>Flag: pwn.college{omhpUARytWmSrjUhVr4mOerpjaC.dBzM4QDL1MzN0czW}
