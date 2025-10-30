#### standard streams
1. standard input (stdin) 0: when any input goes from terminal to shell
2. standard output (stdout) 1: when any process succeeded and output goes from shell to terminal
3. standard error (stderr) 2: when any process failed
#### redirection
- output will go to another place instead of showing on terminal:
```bash
ls -l ~ > output # the result will be written (and overwritten) into output file
ls -l ~ >> output # the result will be appeneded into output file
```

```bash
echo $(date) > date
date >> date
```
- redirect errors:
```bash
ls /err 2>> error
ls /err 2> error
```
- redirect stderr & stdout:
```bash
cat /etc/shadow /etc/hosts 1> success 2> error
```
- redirection for stdin:
```bash
cat < <file_name>
```
#### pipes
the main idea of `pipes`:
each stdout from program can be stdin to another
- basic usage:
```bash
grep ff0 /etc/hosts # search for ff0 inside /etc/hosts
grep ff0 -n /etc/hosts # same as above, but with row number
```
- more about usage:
```bash
grep -r -n ff0 /etc/ # search recursively inside /etc files and subfolders and return results
grep -r -l ff0 /etc/ # search recursively inside /etc files and subfolders and return files names only
```
- how many time the word mentioned:
```bash
grep -cr port /etc/
```
#### filters
- head
```bash
head -n 5 /var/log/syslog # cating first 5 lines
```
- tail
```bash
tail -n 5 /var/log/syslog # cating last 5 lines
```
- wc
```bash
wc -l -w -c /etc/hosts
```

#### back to pipes
- mix between pipes & filters:
```bash
head -n 50 /var/log/syslog | grep scripts
```
- triple them:
```bash
head -n 50 /var/log/syslog | grep scripts | wc -l
```
- assign them to variable
```bash
var1=$(head -n 50 /var/log/syslog | grep scripts | wc -l);
echo $var;
```
