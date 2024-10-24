# Shell Variables
## Printing Variables
>[!TIP]
>To print variables we need to attach `$` prior to the variable in order to print it

here to aquire the flag we need to print the variable `FLAG`, for that we use `$ echo $FLAG` command
```
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{EMJXgEOMFnFXY_r-c3ruEt4uatp.ddTN1QDL1MzN0czW}
```
>Flag: pwn.college{EMJXgEOMFnFXY_r-c3ruEt4uatp.ddTN1QDL1MzN0czW}

## Setting Variables
here to aquire flag we need to assign `COLLEGE` value to `PWN` variable by using `$ PWN=COLLEGE` command
```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{YkGs62i0KrPrIPbDaOpkbqGX6Ql.dlTN1QDL1MzN0czW}
```
>Flag: pwn.college{YkGs62i0KrPrIPbDaOpkbqGX6Ql.dlTN1QDL1MzN0czW}

## Multi-word variables
here to aquire flag we need to assign `COLLEGE YEAH` value to `PWN` variable so we can't perform it directly so we will be using `""`. to perform this task we use `$ PWN="COLLEGE YEAH"` command
```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{Ug9-hKUU1NKp3crg_M9Ro4WlQve.dBjN1QDL1MzN0czW}
```
>Flag: pwn.college{Ug9-hKUU1NKp3crg_M9Ro4WlQve.dBjN1QDL1MzN0czW}

## Exporting Variables
>[!TIP]
>we use `export` command to export variables and make them environment variables

here to aquire flag we need set `COLLEGE` value to `PWN` variable and we need to export it with `$ export PWN=COLLEGE` command and then we need to set `PWN` value to `COLLEGE` variable with `$ COLLEGE=PWN` command and then we need to run `$ /challenge/run` command to get the flag  
```
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{05-OVS9PHNPbqIRYPnNPlYmEaFO.dJjN1QDL1MzN0czW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
>Flag: pwn.college{05-OVS9PHNPbqIRYPnNPlYmEaFO.dJjN1QDL1MzN0czW}

## Printing Exported variables
>[!TIP]
>The `env` commnad is used to view, modify, or clear environment variables for commands. It can display current environment variables, run commands with a modified environment, or start a command with a clean environment using `env -i`

here to get flag we need to run `env` command
```
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
DOJO_AUTH_TOKEN=e3341af3072013fc44261566f46f7668a0da5a293ce22f3a426214d6e66fc766
HOME=/home/hacker
LANG=C.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.7z=01;31:*.ace=01;31:*.alz=01;31:*.apk=01;31:*.arc=01;31:*.arj=01;31:*.bz=01;31:*.bz2=01;31:*.cab=01;31:*.cpio=01;31:*.crate=01;31:*.deb=01;31:*.drpm=01;31:*.dwm=01;31:*.dz=01;31:*.ear=01;31:*.egg=01;31:*.esd=01;31:*.gz=01;31:*.jar=01;31:*.lha=01;31:*.lrz=01;31:*.lz=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.lzo=01;31:*.pyz=01;31:*.rar=01;31:*.rpm=01;31:*.rz=01;31:*.sar=01;31:*.swm=01;31:*.t7z=01;31:*.tar=01;31:*.taz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tgz=01;31:*.tlz=01;31:*.txz=01;31:*.tz=01;31:*.tzo=01;31:*.tzst=01;31:*.udeb=01;31:*.war=01;31:*.whl=01;31:*.wim=01;31:*.xz=01;31:*.z=01;31:*.zip=01;31:*.zoo=01;31:*.zst=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.crdownload=00;90:*.dpkg-dist=00;90:*.dpkg-new=00;90:*.dpkg-old=00;90:*.dpkg-tmp=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:*.swp=00;90:*.tmp=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:
FLAG=pwn.college{YT6RZ6-t_s3dwXkX0PRA2cjUvz1.dhTN1QDL1MzN0czW}
LESSCLOSE=/usr/bin/lesspipe %s %s
TERM=xterm
LESSOPEN=| /usr/bin/lesspipe %s
SHLVL=1
LC_CTYPE=C.UTF-8
PATH=/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
_=/run/workspace/bin/env
```
>Flag: pwn.college{YT6RZ6-t_s3dwXkX0PRA2cjUvz1.dhTN1QDL1MzN0czW}

## Storing command output
here to aquire flag we need to run `/challenge/run` program and store output in `PWN` variable using `$ PWN=$(/challenge/run)` command and we have to print the output of `PWN` using `$ echo "$PWN"` command
```
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo "$PWN"
pwn.college{o1N2M203uzryC5RY6LOBZHL1wYH.dVzN0UDL1MzN0czW}
```
>Flag: pwn.college{o1N2M203uzryC5RY6LOBZHL1wYH.dVzN0UDL1MzN0czW}

## Reading Input
here to aquire flag we need to use `read` command to set value `COLLEGE` to variable `PWN`, for this we use `$ read PWN` command and we will give `COLLEGE` as input
then we will get the flag
```
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{YxidloAoozxg1fQbSGhEks0p07b.dhzN1QDL1MzN0czW}
```
>Flag: pwn.college{YxidloAoozxg1fQbSGhEks0p07b.dhzN1QDL1MzN0czW}

## Reading files
Here to aquire flag we need to read program `/challenge/read_me` into `PWN` variable using `$ read PWN < /challenge/read_me` command
```
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{U71HpXj6-0kRK74JVI13cpnYOi-.dBjM4QDL1MzN0czW}
```
>Flag: pwn.college{U71HpXj6-0kRK74JVI13cpnYOi-.dBjM4QDL1MzN0czW}
