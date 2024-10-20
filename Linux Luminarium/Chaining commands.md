# Chaining commnands
## Chaining with semicolons
>[!TIP]
>We use `;` to give more than one command as input to terminal

Here to aquire flag we need to run `/challenge/pwn` and `/challenge/college` files as single input, for that we use `$ /challenge/pwn; /challenge/college` command to get the flag
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{4QqA7K_Daih1nOAmJwBZxP9MCBj.dVTN4QDL1MzN0czW}
```
>Flag: pwn.college{4QqA7K_Daih1nOAmJwBZxP9MCBj.dVTN4QDL1MzN0czW}

## Your first shell script
>[!TIP]
>We use `nano` command to edit text and to write scripts in a file like group of commands etc by passing file name as argument and it behaves as a text editor
>[!TIP]
>we use `bash` command to execute files by giving file name as argument

Here to aquire flag we need to create a file `x.sh` and we need to store these two `/challenge/pwn` and `/challenge/college,` commands in it and then we need to execute `x.sh` file using `$ bash x.sh` command to get the flag
```
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{Ah6u9tTRGxrqrbhqXmQsVKTRK-I.dFzN4QDL1MzN0czW}
```
>Flag: pwn.college{Ah6u9tTRGxrqrbhqXmQsVKTRK-I.dFzN4QDL1MzN0czW}

## Redirecting script output
>[!TIP]
>All of the various redirection methods work: `>` for stdout, `2>` for stderr, `<` for stdin, `>>` and `2>>` for append-mode redirection, `>&` for redirecting to other file descriptors, and `|` for piping to another command.

Here to aquire flag we need to pipe the output of `x.sh` file which we have created in the previous challenge to the `/challenge/solve` command to get the flag
```
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{kuBPMm9GA3YzCh8MX_wgdRVvL6r.dhTM5QDL1MzN0czW}
```
>Flag: pwn.college{kuBPMm9GA3YzCh8MX_wgdRVvL6r.dhTM5QDL1MzN0czW}
