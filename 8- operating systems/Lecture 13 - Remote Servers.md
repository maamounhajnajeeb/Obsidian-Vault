## OpenSSh with basic authentication (username and password)
###### connect to remote server via IP Address:
```bash
ssh <IP Address on Domain name>
```
then you have to put fingerprint or user password of the remote machine.
###### how to know who is logged in into the machine?
using `w` command:
```bash
w
```
###### how to see daemon details of ssh?
```bash
ps -elf | grep sshd
```
###### another way to connect to remote server via ssh:
```bash
ssh <username>@<Ip Address>
```
##### About known hosts:
each Linux server you connect has some keys, when you connect to the machine and authorize on it, it will send all of its keys to your local machine, these keys saved in known_host file, so in the next time you connect it will be used to reduce redundant authorization processes.
`known_hosts` file located at: `~/.ssh/known_hosts`.
###### third way: execute commands on remote without connecting to it:
```bash
ssh < username@<IP Address or Hostname> > <any commmand>
```
###### Aliasing remote server names:
first, we need to jump into `.ssh/` directory, then creating `config` file (if not existed), then open the `config` file with any text editor (nano, vi, ...).
###### config file content:
```txt
Host Albunyan_Almarsous
  Hostname <IP Address>
  Port 22
  User <user name>
```
then just type:
```bash
ssh Albunyan_Almarsous
```
## Transferring Data Between server and local
there are two tools for this task: `scp`, `rsync`, `wget`, `curl`
###### rsync:
it transfer files and do synchronization.
###### wget:
it let you download directly to Linux.
it also supports the resume download.
###### curl:
very powerful to interact with internet.
## Terminal based web browser:
there are some tools to achieve that, like: `lynx`
