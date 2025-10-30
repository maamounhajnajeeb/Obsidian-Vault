#### clear command
- clear terminal (use ctrl + a)
```bash
clear
```
#### ls command
1. show all folders and files
```bash
ls -a
```
2. show folders and files as list
```bash
ls -a -l
```
3. show files and folders (folders will have appended /)
```bash
ls -a -F
```
4. you can do this ls shortcut
```bash
ls -alF
```
5. ls docs
```bash
ls --help
```
#### home directory
`home directory`: is a directory created for each user, usually located like this: `/home/<username>`
- how to access home directory from wherever you are?
```bash
cd ~
```
#### access top directory
using this command will direct you to Linux top directory (something like C drive in Win)
```bash
cd /
```
after that, if you write list command, it will shows you all folders and files which installed by default with Linux.
![[top_dir.png]]
#### command type
to get command type (command source and original path):
```bash
type -a <command_name>
```
#### command manual
to get any command full manual:
```bash
man <command_name>
```
#### current user
to get user current username:
```bash
whoami
```
#### command session history
```bash
history
```
#### change file timestamps
update  the  access  and  modification  times of each FILE to the current time.
```bash
touch <file_name>
```
`note`: fastest way to create new file is with touch.
#### deleting non-empty folders
this command will recursively delete the directory and it's content
```bash
rm -r <path/to/dir>
```
#### print files content
<b>cat</b> command will concatenate files and print on the standard output
```bash
cat <first_file> <second_file> ...
```
<b>cat</b> could be used with one file or more
#### Root user
<b>root</b> user is a pre-built user that has all permissions, because of that it's <i>dangerous</i>.
if I want to run a command from root, you can do this in two ways:
1. sign in with root credentials
2. user `sudo` to execute commands as user, but normal user who executes commands via `sudo` needs privileges from distro/root user to use it (not for everybody).
