## Ownership:
by default the user who created the file is the ownership of this file.
when user created a file or directory, not just user owns the file or directory, the primary group of the owner user owns the file or directory too.
- example:
```bash
maamoun-haj-najeeb@maamoun-HP-Laptop:~$ ls -l
total 36
drwxr-xr-x  3 maamoun-haj-najeeb maamoun-haj-najeeb 4096 Nov 19 09:44 Desktop
# first name is for user owner, second name is group owner
```
###### but what ownership actually means?
the owner of a file can change the file settings and change the permission of the file.
###### how to change user primary group?
```bash
sudo usermod -g admins sami # -g stands for primary group
# admins stands for the group
# sami stands for user
```
###### how to change ownership of file or directory?
using `chown` command
```bash
sudo chown user1:user1 <filename>
# <user owner>: <group owner>  <the name of the file>
```
## Permissions:
- permissions at Linux are three type:
1. read (r)
2. write (w)
3. execute (x) (execute for a directory is like `cd` command)
- permissions for each file separated into three types:
1. owner (user) permission
2. owner group permissions
3. others
```bash
-rw-rw-r--  1 maamoun-haj-najeeb maamoun-haj-najeeb    0 Nov 19 11:27 somefile
# rw- for user
# rw- for group
# r-- for others
```
- the three types called (9 dashes or permissions) called the file mode or directory mode
- each permission has numeric representation:
1. read: 4
2. write: 2
3. execute: 1
###### how to edit file or directory permission?
using `chmod` command:
```bash
sudo chmod u=rwx,g=---,o=--- <file name>
sudo chmod ug+x <file name> # for user and group
sudo chmod 744 <file name>
```
###### how to get the access control list of a file (to edit other permission)?
```bash
getfacl <file name> -t # -t for table view
# result
# file: somfile
# USER   maamoun-haj-najeeb  rwx     
# GROUP  maamoun-haj-najeeb  r--     
# other
```
###### how to give a user special permission on file or directory?
```bash
setfacl -m u:user1:r <file name>
```
and a `+` will appear in the end of the permission list
