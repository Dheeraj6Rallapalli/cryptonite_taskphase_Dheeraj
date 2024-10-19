# Untangling Users
## Becoming root with su
>[!TIP]
>We use `su` command to change the user

Here to aquire flag we need change the user using `$ su` command and then we need to enter the password `hack-the-planet` so that we user gets changed then we need to spectate the files in it using `$ ls` command and then we need to read the files using `cat not-the-flag` command to get the flag
```
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# ls
COLLEGE  PWN      d             leap    not-the-flag  the-flag
Desktop  college  instructions  myflag  output.txt
root@users~becoming-root-with-su:/home/hacker# cat not-the-flag
pwn.college{4H9_XZPw5EGQ6_QjINDVw8aiF6_.dVTN0UDL1MzN0czW}
```
>Flag: pwn.college{4H9_XZPw5EGQ6_QjINDVw8aiF6_.dVTN0UDL1MzN0czW}

## Other users with su
here to aquire flag we need change the user to `zardus` using `$ su zardus` command and then we need to enter password `dont-hack-me` then the user is changed and then we need to run `$ /challenge/run` program to get the flag
```
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{klprKmwm-dYjVesQYEZCtZc-Abn.dZTN0UDL1MzN0czW}
```
>Flag: pwn.college{klprKmwm-dYjVesQYEZCtZc-Abn.dZTN0UDL1MzN0czW}

## Cracking passwords
Here to aquire flag we need to read the `/challenge/shadow-leak` file using `$ cat /challenge/shadow-leak` and then we need to search for `zardus` password which we will get to know that it is not cracked then we will use `john` command using `$ john /challenge/shadow-leak` then we will get to know that the password is `aardvark` then we will use `$ su zardus` command to switch the user and the password is mentioned above then we will run `$ /challenge/run` command to get the flag
```
hacker@users~cracking-passwords:~$ cat /challenge/shadow-leak
root:*:19873:0:99999:7:::
daemon:*:19873:0:99999:7:::
bin:*:19873:0:99999:7:::
sys:*:19873:0:99999:7:::
sync:*:19873:0:99999:7:::
games:*:19873:0:99999:7:::
man:*:19873:0:99999:7:::
lp:*:19873:0:99999:7:::
mail:*:19873:0:99999:7:::
news:*:19873:0:99999:7:::
uucp:*:19873:0:99999:7:::
proxy:*:19873:0:99999:7:::
www-data:*:19873:0:99999:7:::
backup:*:19873:0:99999:7:::
list:*:19873:0:99999:7:::
irc:*:19873:0:99999:7:::
gnats:*:19873:0:99999:7:::
nobody:*:19873:0:99999:7:::
_apt:*:19873:0:99999:7:::
hacker::20000:0:99999:7:::
zardus:$6$g9EUYNRhNDbXikSg$sEdQd0yKsBLVtCWMQUBQtOEcB5c0OCgxKpuvTo.AwoS.pz62TyuURTbjJPgNdEFMcVHxtNcL7NkbQTklYiMzi1:20015:0:99999:7:::
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Created directory: /home/hacker/.john
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04833g/s 281.4p/s 281.4c/s 281.4C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{QQzYPhNDPTd9C9ej28_gPHT2eKA.ddTN0UDL1MzN0czW}
```
>Flag: pwn.college{QQzYPhNDPTd9C9ej28_gPHT2eKA.ddTN0UDL1MzN0czW}

## Using sudo
>[!TIP]
>We use `sudo` command to access anything as administrator

Here to aquire flag we need to check all the files with `$ ls` command and then we need to read the `not-the-flag` using `sudo` keyword using `$ sudo cat not-the-flag` command to get the flag
```
hacker@users~using-sudo:~$ ls
COLLEGE  PWN      d             leap    not-the-flag  the-flag
Desktop  college  instructions  myflag  output.txt
hacker@users~using-sudo:~$ cat not-the-flag
cat: not-the-flag: Permission denied
hacker@users~using-sudo:~$ sudo cat not-the-flag
pwn.college{8mdAs-3c-HbrOwgC2YDp4yU9FXh.dhTN0UDL1MzN0czW}
```
>Flag: pwn.college{8mdAs-3c-HbrOwgC2YDp4yU9FXh.dhTN0UDL1MzN0czW}
