# Group Management:
## see groups database
```bash
cat /etc/group/
```
## user groups
if we use this command without username, it will return current user groups. Else, it will show groups for specified user
```bash
groups <username (optional)>
```
## groups philosophy
- Linux creates a group for each user when created, and assign this group as the primary group for that user.
- when I create a file, the ownership for that account belongs to me and my primary group.
## creating group
- use `groupadd` command
```bash
sudo groupadd <groupname>
```
## deleting group
delete group using `groupdel` command:
```bash
sudo groupdel <group name>
```
## adding user to group
- use `usermod` command
```bash
sudo usermod -aG <group name> <username>
```
## deleting user from group
- use `usermod` command with `-rG` tag:
```bash
sudo usermod -rG <group name> <username>
```

# File Management
## see file hierarchy:
- use `tree` command with sudo:
```bash
sudo tree
```
- each file in Linux contain three labels:
1. file name
2. data block (addresses for memory)
3. inode: meta-data for that file (creation time, ...)
- how to see inode details?
  using `stat` command
```bash
stat <filename>
```
## Links (shortcut in windows):
it has two types:
### hard link
- another filename for the same inode, for same data block.
- if I change content of any file, it will affect the other one.
- the two files will be different only in the file name, data block and inode are the same.
example:
```bash
ln <original file> <new file>
```
### soft link
- same concept in Windows, just another way to access the file.
- the inode is different, also the file name
- data block is the same between two files, any content change in one file will affect the second. 
example:
```bash
ln -s <original file> <new file>
```
### Showing inode number in files listing:
```bash
ls -il
```
### what happen if we delete the original file
the hard link will stay, soft link bye bye.