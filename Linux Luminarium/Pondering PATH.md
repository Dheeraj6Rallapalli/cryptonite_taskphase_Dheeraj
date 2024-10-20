# Pondering PATH
## The PATH Variable 
>[!TIP]
>There is a special shell variable, called PATH, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands

Here to aquire flag we need to remove the contents in the `PATH` variable by assigning nothing to it using `$ PATH=""` command and then we need to run `$ /challenge/run` command so that it can't delete the flag and gives you the flag
```
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{AxOaSWVaQAWf97kBEHCkzBv73fB.dZzNwUDL1MzN0czW}
```
>Flag: pwn.college{AxOaSWVaQAWf97kBEHCkzBv73fB.dZzNwUDL1MzN0czW}

## Setting PATH
Here to aquire flag we need to assign the `/challenge/more_commands/` path to `PATH` shell variable so that `win` command will get into the `PATH` variable so when we run `$ /challenge/run` command `win` will be launched and we will get our flag
```
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{kbp8siZXuD0WrW8677MUpwLnHyP.dVzNyUDL1MzN0czW}
```
>Flag: pwn.college{kbp8siZXuD0WrW8677MUpwLnHyP.dVzNyUDL1MzN0czW}

## Adding Comands
Here to aquire flag we need to add `cat /flag` command to `win` file using `nano win` command and then we need change the mode of the file so that it is executable and then we need to append `/home/hacker` to `PATH` for that we use `$ PATH=$PATH:/home/hacker` command and then we will run `/challenge/run` to get the flag
```
hacker@path~adding-commands:~$ chmod +x win
hacker@path~adding-commands:~$ echo $PATH
/nix/store/3v4hdb2gmpj7jv2z848ikakhzl9rjgwh-code-server/libexec/code-server/lib/vscode/bin/remote-cli:/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~adding-commands:~$ PATH=$PATH:/home/hacker
hacker@path~adding-commands:~$ echo $PATH
/nix/store/3v4hdb2gmpj7jv2z848ikakhzl9rjgwh-code-server/libexec/code-server/lib/vscode/bin/remote-cli:/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/home/hacker
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{k-PtfyHU4wgDtJGwTaXdYzmB9-_.dZzNyUDL1MzN0czW}
```
>Flag: pwn.college{k-PtfyHU4wgDtJGwTaXdYzmB9-_.dZzNyUDL1MzN0czW}

## Hijacking commands
Here to aquire flag we need to create a `rm` command which invokes `cat /flag` command using  `$ nano rm` command and then we need to make `rm` an executable command and then we need place `/home/hacker` file in the first so that it reads the `rm` file which we created first for that we need to add `/home/hacker` file to the `PATH` in the left for that we use `$ PATH=/home/hacker:$PATH` command and then we will run `/challenge/run` command to get the flag
```
hacker@path~hijacking-commands:~$ nano rm
hacker@path~hijacking-commands:~$ chmod +x rm
hacker@path~hijacking-commands:~$ PATH=/home/hacker:$PATH
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/rm. Executing!
pwn.college{k19ROWzusSPn-4rdwBIA9ggdmnz.ddzNyUDL1MzN0czW}
```
>Flag: pwn.college{k19ROWzusSPn-4rdwBIA9ggdmnz.ddzNyUDL1MzN0czW}
