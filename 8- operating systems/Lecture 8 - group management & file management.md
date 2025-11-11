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
