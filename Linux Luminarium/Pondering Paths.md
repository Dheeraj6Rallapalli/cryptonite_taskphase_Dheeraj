# Pondering Paths
## The Root
Type `$ /pwn` to get the flag

here `/` helps to go through the path
```
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{sVGWix7R9QNk8AOqawKw2ZuYHtA.dhzN5QDL1MzN0czW}
```
>Flag: pwn.college{sVGWix7R9QNk8AOqawKw2ZuYHtA.dhzN5QDL1MzN0czW}
## Program and absolute paths
Type `$ /challenge/run` to get the flag

here we are accesing a program `run` in `challenge` directory
```
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{AjpUYLPjEtyksOjOwxZVdL1c11M.dVDN1QDL1MzN0czW}
```
>Flag: pwn.college{AjpUYLPjEtyksOjOwxZVdL1c11M.dVDN1QDL1MzN0czW}

## Position thy self
Type `$ cd /usr/share/zoneinfo/posix/Asia` to enter in to the directory

Type `$ /challenge/run` to get the flag

here we use `cd` to navigte through the directory
```
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/zoneinfo/posix/Asia directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /usr/share/zoneinfo/posix/Asia
hacker@paths~position-thy-self:/usr/share/zoneinfo/posix/Asia$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{gUiA-FvRHC2NCkeQOGy6eDRVEii.dZDN1QDL1MzN0czW}
```
>Flag: pwn.college{gUiA-FvRHC2NCkeQOGy6eDRVEii.dZDN1QDL1MzN0czW}

## Position elsewhere
Type `$ cd /usr/share/doc/fontconfig` to enter in to the directory

Type `$ /challenge/run` to get the flag
```
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc/fontconfig directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /usr/share/doc/fontconfig
hacker@paths~position-elsewhere:/usr/share/doc/fontconfig$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{U08lBtzXfRXja8wuRmqcgs7WPKe.ddDN1QDL1MzN0czW}
```
>Flag: pwn.college{U08lBtzXfRXja8wuRmqcgs7WPKe.ddDN1QDL1MzN0czW}

## Position yet elsewhere
Type `$ cd /var/lib/apt/lists` to enter in to the directory

Type `$ /challenge/run` to get the flag

here `~` will show our current shell location
```
hacker@paths~position-yet-elsewhere:~$ ~
bash: /home/hacker: Is a directory
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /var/lib/apt/lists directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /var/lib/apt/lists
hacker@paths~position-yet-elsewhere:/var/lib/apt/lists$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{cm3Sufj-txB3suPdgdbCaE7Uk6q.dhDN1QDL1MzN0czW}
```
>Flag: pwn.college{cm3Sufj-txB3suPdgdbCaE7Uk6q.dhDN1QDL1MzN0czW}

## Implicit relative paths, from /
Type `$ cd /` to enter into directory

Type `$ challenge run` to get the flag

here the cwd is `/` and relative path is `challenge/run`
```
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{8unUu-TsKysth89SLNlhM5P7A6X.dlDN1QDL1MzN0czW}
```
>Flag: pwn.college{8unUu-TsKysth89SLNlhM5P7A6X.dlDN1QDL1MzN0czW}

## Explicit relative paths, from/
Type `$ cd /` to enter into directory

Type `$ ./challenge/run` to get the flag

here `.` refers to present directory


```
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{MPk5Q5VmnJP8BGGyxOOc54XTe-2.dBTN1QDL1MzN0czW}
```
>Flag: pwn.college{MPk5Q5VmnJP8BGGyxOOc54XTe-2.dBTN1QDL1MzN0czW}

## Implicit relative path
Type `$ cd /challenge` to enter in to the directory

Type `$ ../challenge/run` to get the flag

here by using `..` we will run the file explicitly
```
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ../challenge/run
Correct!!!
../challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{YwwshkXLYpE-eaKUZlt5YgUZn5P.dFTN1QDL1MzN0czW}
```
>Flag: pwn.college{YwwshkXLYpE-eaKUZlt5YgUZn5P.dFTN1QDL1MzN0czW}

## Home sweet home
Type `$ /challenge/run ~/d` will copy the file in `/challang/run` to `/d` and we will get the flag

here we are copying the file to home and we are reading it
```
hacker@paths~home-sweet-home:~$ /challenge/run ~/d
Writing the file to /home/hacker/d!
... and reading it back to you:
pwn.college{ARk4aeaUxma-mIJr8e48ayOCGJz.dNzM4QDL1MzN0czW}
```
>Flag: pwn.college{ARk4aeaUxma-mIJr8e48ayOCGJz.dNzM4QDL1MzN0czW}
