#### working on remote host
1. download openssh-server
```bash
sudo apt update & apt install openssh-server -y
```
2. connect
```bash
ssh <username>@<host>
ssh maamounhajnajeeb@localhost # example
```
3. check that you are at remote
```bash
ps # it should show that TTY is pts/1 or pts/2 ...
```
4. to exit
```bash
exit
```
#### working with other shells
1. see other shells
```bash
ls /bin/*sh
```
#### shell expansion
1. brace expansion: to create too many files in one command, or list them
```bash
touch file{4..11}
```

```bash
ls file{1..5}
```
2. astrick to replace anything or nothing
```bash
ls file*
```
3. question mark will replace one character
```bash
ls file? # give all results with one charachter after file word
```
4. square braces expansion
```bash
ls file[!2] # everything with one digit except file2
```

```bash
ls file[1-3] # list files from file1 -> file3
```
5. regular expression expansion
```bash

```
#### shell variables
1. build variable
```bash
var1=1;
echo $var1;
```
2. default values with echo
```bash
echo ${var3-unset} # if there is no var3 in the memory, it will print unset
```
#### variables substitution
it means encapsulate the output of the command and put it in (variable/stdout/to redirect...)
1. variable can be a value of arithmetic operation
```bash
var3=$[1 + 2]
```
2. or variable can be a value of function call
```bash
var4=$(date)
```
#### exit code
echo this to show exit code for any command
```bash
echo $? # any none 0 exit code will be error, 0 means success
```
#### show all variables
```bash
compgen -v
```

#### defining variables
```bash
declare -i a
a=10
```
#### how to evaluate an expression
the safest way is to use `expr`
```bash
expr 1 + 2
```
#### how to differentiate between login-shell and non-login shell
```bash
echo $0 # if the result -bash it is login shell, without dash it is non-login shell
```
#### how to define variables permanently
edit `.bashrc` and put whatever variables you want
