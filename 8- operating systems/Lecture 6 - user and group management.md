## overview of users in Linux
![[linux_users.png]]
examples:
1. see all users (without passwords)
```bash
cat /etc/passwd
```
2. trick: get specific user data by entering his name
```bash
cat /etc/passwd | grep root # or any user name
```
3. see all users with hashed passwords
```bash
sudo cat /etc/shadow
```
## adding users
use `useradd` or `adduser` commands:
```bash
useradd maamoun -c "Maamoun Haj Najeeb"
```
## deleting users
use `userdel`:
```bash
userdel maamoun # add -r if user has home directory
```
### change password
use `passwd`:
```bash
passwd sayed # change the name depending on the username
```
## change user
```bash
su <username>
```
## edit user data
we can change user group, username, password... via this command:
```bash
usermod <username>
```
