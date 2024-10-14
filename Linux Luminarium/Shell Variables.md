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
