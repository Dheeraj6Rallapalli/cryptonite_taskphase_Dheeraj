# Digesting Documentation
## Learning from documentation
>[!TIP]
>Documentation specifies us which argument to be passed to a command it order in to give required output

here to aquire flag we need to pass correct argument to this `/challenge/challenge` so that we get flag, that is we use `$ /challenge/challenge --giveflag` command which means this`--giveflag`
is argument
```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{MJk9UKfmm8thxz14MPXfLwpFb_A.dRjM5QDL1MzN0czW}
```
>Flag: pwn.college{MJk9UKfmm8thxz14MPXfLwpFb_A.dRjM5QDL1MzN0czW}
## Learning Complex Usage
here to get the flag we need to find the argument for `--printfile` argument, to find it we will check the directories then we will find it in `/` so the command to get the flag is
`$ /challenge/challenge --printfile /flag`
```
hacker@man~learning-complex-usage:~$ cd /challenge
hacker@man~learning-complex-usage:/challenge$ ls
DESCRIPTION.md  challenge
hacker@man~learning-complex-usage:/challenge$ cd /
hacker@man~learning-complex-usage:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{UwbErQJMcmxbF2RrkSiOXM0LIe1.dVjM5QDL1MzN0czW}
```
>
>Flag: pwn.college{UwbErQJMcmxbF2RrkSiOXM0LIe1.dVjM5QDL1MzN0czW}

## Reading Manuals
>[!TIP]
>we use `man` command to get the mannual of a command which we pass as an argument

here to aquire the flag we need to read the mannual of `challenge` and follow the instructions over there
```
hacker@man~reading-manuals:~$ man challenge

CHALLENGE(1)                  Challenge Commands                  CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --goudeh NUM
              print the flag if NUM is 271

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The  repository for this dojo: <https://github.com/pwncollege/linux-lu‐
       minarium/>

SEE ALSO
       man(1) bash-builtins(7)

pwn.college                        May 2024                       CHALLENGE(1)
hacker@man~reading-manuals:~$ /challenge/challenge --goudeh 271
Correct usage! Your flag: pwn.college{goE271uJde7hRXhbXiBgqlZ4RZr.dRTM4QDL1MzN0czW}
```
>Flag: pwn.college{goE271uJde7hRXhbXiBgqlZ4RZr.dRTM4QDL1MzN0czW}

## Searching Manuals
here to aquire flag we need to find the flag in mannual of `challenge` command and there we will find it using`$ /flag` command so that we get argument for `/challenge/challenge` which is ` --gzowb`
```

NAME
       /challenge/challenge - print the flag!
       --ginjuu
              This argument will give you the flag!
```
```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge  --ginjuu
Initializing...
Correct usage! Your flag: pwn.college{I45SFWIdpo7rRYO7mrjWrComdx7.dVTM4QDL1MzN0czW}
```
>Flag: pwn.college{I45SFWIdpo7rRYO7mrjWrComdx7.dVTM4QDL1MzN0czW}

## Searching for files
we will checkout the `$ man man` command as specified in the question, reveals the manual page for the man command. Scrolling down reveals a FINDING MANUAL PAGES section where we will see an option called --wildcard. It takes a string as an argument and searches for that string in the other manual pages.
```
--wildcard
              Show  all pages with any part of either their names or their de‐
              scriptions matching each page argument using  shell-style  wild‐
              cards,  as  with  apropos(1) --wildcard.  The page argument must
              match the entire name or description, or match  on  word  bound‐
              aries  in the description.  Since there is usually no reasonable
              way to pick a "best" page when searching for  a  wildcard,  this
              option implies -a.
```
Using `--wildcard` as argument for `man` will give mannual for `flag` using `$ man --wildcard flag
` which gives flag information. Running the command `$ /challenge/challenge --wshisl 703`
gives the flag.
```
hacker@man~searching-for-manuals:~$ man --wildcard flag

CHALLENGE(1)                  Challenge Commands                  CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --wshisl NUM
              print the flag if NUM is 703

AUTHOR
       Written by Zardus.
hacker@man~searching-for-manuals:~$ 
hacker@man~searching-for-manuals:~$ /challenge/challenge --wshisl 703
Correct usage! Your flag: pwn.college{wNs7h0iPslulQTyby3kR-DhLKXB.dZTM4QDL1MzN0czW}
```
>Flag: pwn.college{wNs7h0iPslulQTyby3kR-DhLKXB.dZTM4QDL1MzN0czW}
