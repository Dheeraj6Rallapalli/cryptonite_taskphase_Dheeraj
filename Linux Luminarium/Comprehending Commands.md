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

## Removing Files
>[!TIP]
>we use `rm` command to remove files by giving file name as argument

here to aquire flag we will remove a file by using `$ rm delete_me` command and we will run `$ /challenge/check` command
```
hacker@commands~removing-files:~$ ls
Desktop  college  d  delete_me  leap
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{0hdpk67ig-W3wkNP6S8i38JrnwJ.dZTOwUDL1MzN0czW}
```
>Flag: pwn.college{0hdpk67ig-W3wkNP6S8i38JrnwJ.dZTOwUDL1MzN0czW}

## Hidden Files
>[!TIP]
>with `ls` command we can't list all file so we use `ls -a` to list hidden files like fils start with ' . '

here to aquire the flag we need to list the hidden files in `/` so we use `$ ls -a /` and then we will read the flag file with `$ cat /.flag-1245055329992` command
```
hacker@commands~hidden-files:~$ ls -a /
.           .flag-1245055329992  challenge  home   lib64   mnt  proc  sbin  tmp
..          bin                  dev        lib    libx32  nix  root  srv   usr
.dockerenv  boot                 etc        lib32  media   opt  run   sys   var
hacker@commands~hidden-files:~$ cat /.flag-1245055329992
pwn.college{QX4RCf-kXnylFGiAkFDn-lhj2fE.dBTN4QDL1MzN0czW}
```
>Flag: pwn.college{QX4RCf-kXnylFGiAkFDn-lhj2fE.dBTN4QDL1MzN0czW}

## An Epic Filesystem Quest
here to aquire flag follow given instructions
```
hacker@commands~an-epic-filesystem-quest:~$ ls /
SPOILER  challenge  flag  lib32   media  opt   run   sys  var
bin      dev        home  lib64   mnt    proc  sbin  tmp
boot     etc        lib   libx32  nix    root  srv   usr
hacker@commands~an-epic-filesystem-quest:~$ cat /flag
cat: /flag: Permission denied
hacker@commands~an-epic-filesystem-quest:~$ cat /SPOILER
Congratulations, you found the clue!
The next clue is in: /usr/share/racket/pkgs/web-server-lib/web-server/stuffers/compiled

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:~$ ls -a /usr/share/racket/pkgs/web-server-lib/web-server/stuffers/compiled
.               gzip_rkt.dep       hmac-sha1_rkt.zo   stuffer_rkt.dep
..              gzip_rkt.zo        serialize_rkt.dep  stuffer_rkt.zo
.REVELATION     hash_rkt.dep       serialize_rkt.zo
base64_rkt.dep  hash_rkt.zo        store_rkt.dep
base64_rkt.zo   hmac-sha1_rkt.dep  store_rkt.zo
hacker@commands~an-epic-filesystem-quest:~$ cat /usr/share/racket/pkgs/web-server-lib/web-server/stuffers/compiled/.REVELATION
Congratulations, you found the clue!
The next clue is in: /usr/lib/python3/dist-packages/prompt_toolkit/contrib/completers/__pycache__
hacker@commands~an-epic-filesystem-quest:~$ ls /usr/lib/python3/dist-packages/prompt_toolkit/contrib/completers/__pycache__
NOTE  __init__.cpython-38.pyc  system.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:~$ cat /usr/lib/python3/dist-packages/prompt_toolkit/contrib/completers/__pycache__/NOTE
Lucky listing!
The next clue is in: /opt/aflplusplus/nyx_mode/libnyx/libnyx/target/release/build/standback-2f6bd496193f0fe7

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:~$ ls /opt/aflplusplus/nyx_mode/libnyx/libnyx/target/release/build/standback-2f6bd496193f0fe7
TEASER-TRAPPED      build_script_build-2f6bd496193f0fe7
build-script-build  build_script_build-2f6bd496193f0fe7.d
hacker@commands~an-epic-filesystem-quest:~$ cat /opt/aflplusplus/nyx_mode/libnyx/libnyx/target/release/build/standback-2f6bd496193f0fe7/TEASER-TRAPPED
Tubular find!
The next clue is in: /usr/share/icons/hicolor/72x72/stock/text
hacker@commands~an-epic-filesystem-quest:~$ ls /usr/share/icons/hicolor/72x72/stock/text
GIST
hacker@commands~an-epic-filesystem-quest:~$ cat /usr/share/icons/hicolor/72x72/stock/text/GIST
Congratulations, you found the clue!
The next clue is in: /opt/aflplusplus/nyx_mode/QEMU-Nyx/linux-user/host/ppc

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:~$ ls /opt/aflplusplus/nyx_mode/QEMU-Nyx/linux-user/host/ppc
ALERT-TRAPPED  hostdep.h
hacker@commands~an-epic-filesystem-quest:~$ cat /opt/aflplusplus/nyx_mode/QEMU-Nyx/linux-user/host/ppc/ALERT-TRAPPED
Yahaha, you found me!
The next clue is in: /opt/aflplusplus/qemu_mode/qemuafl/capstone

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:~$ ls /opt/aflplusplus/qemu_mode/qemuafl/capstone
WHISPER
hacker@commands~an-epic-filesystem-quest:~$ cd /opt/aflplusplus/qemu_mode/qemuafl/capstone
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/capstone$ cat WHISPER
Yahaha, you found me!
The next clue is in: /usr/share/nvim/runtime/indent
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/capstone$ ls /usr/share/nvim/runtime/indent
CLUE            eiffel.vim           matlab.vim    scss.vim
aap.vim         erlang.vim           mf.vim        sdl.vim
ada.vim         eruby.vim            mma.vim       sh.vim
ant.vim         eterm.vim            mp.vim        sml.vim
automake.vim    falcon.vim           nsis.vim      sql.vim
awk.vim         fortran.vim          objc.vim      sqlanywhere.vim
bib.vim         framescript.vim      ocaml.vim     systemd.vim
bst.vim         gitconfig.vim        occam.vim     systemverilog.vim
bzl.vim         gitolite.vim         pascal.vim    tcl.vim
c.vim           go.vim               perl.vim      tcsh.vim
cdl.vim         haml.vim             perl6.vim     teraterm.vim
ch.vim          hamster.vim          php.vim       tex.vim
chaiscript.vim  hog.vim              postscr.vim   tf.vim
changelog.vim   html.vim             pov.vim       tilde.vim
clojure.vim     htmldjango.vim       prolog.vim    treetop.vim
cmake.vim       idlang.vim           pyrex.vim     typescript.vim
cobol.vim       ishd.vim             python.vim    vb.vim
config.vim      j.vim                r.vim         verilog.vim
context.vim     java.vim             raml.vim      vhdl.vim
cpp.vim         javascript.vim       readline.vim  vim.vim
cs.vim          javascriptreact.vim  rhelp.vim     vroom.vim
css.vim         json.vim             rmd.vim       wast.vim
cucumber.vim    jsp.vim              rnoweb.vim    xf86conf.vim
cuda.vim        ld.vim               rpl.vim       xhtml.vim
d.vim           less.vim             rrst.vim      xinetd.vim
dictconf.vim    lifelines.vim        rst.vim       xml.vim
dictdconf.vim   liquid.vim           ruby.vim      xsd.vim
docbk.vim       lisp.vim             rust.vim      xslt.vim
dosbatch.vim    logtalk.vim          sas.vim       yacc.vim
dtd.vim         lua.vim              sass.vim      yaml.vim
dtrace.vim      mail.vim             scala.vim     zimbu.vim
dylan.vim       make.vim             scheme.vim    zsh.vim
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/capstone$ cat /usr/share/nvim/runtime/indent/CLUE
Yahaha, you found me!
The next clue is in: /etc/ufw/applications.d/apache2

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/capstone$ ls /etc/ufw/applications.d/apache2
NUGGET-TRAPPED
hacker@commands~an-epic-filesystem-quest:/opt/aflplusplus/qemu_mode/qemuafl/capstone$ cat /etc/ufw/applications.d/apache2/NUGGET-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{kQ5lRtcj1AJCjxJOAS9_-TX-mNQ.dljM4QDL1MzN0czW}
```
>Flag: pwn.college{kQ5lRtcj1AJCjxJOAS9_-TX-mNQ.dljM4QDL1MzN0czW}

## Making Directories
>[!TIP]
>we use `mkdir` to make directories by giving path as argument

here to aquire flag we need to make a directory by using `$ mkdir /tmp/pwn` command and then we will create a file in it
by using `$ touch college` and then we run `$ /challenge/run` command
```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ ls /tmp
bin  hsperfdata_root  pwn  tmp.XvrUsDZh8M
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ ls
college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{sIVOoHwPJ_sz3dsMdhxaBiLADVy.dFzM4QDL1MzN0czW}
```
>Flag: pwn.college{sIVOoHwPJ_sz3dsMdhxaBiLADVy.dFzM4QDL1MzN0czW}
