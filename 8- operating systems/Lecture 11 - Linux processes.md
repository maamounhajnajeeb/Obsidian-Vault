###### how to see processes in this user terminal?
```bash
ps
```
###### how to see processes for all users?
```bash
ps -e
```
- what really matters isn't the command, what really matters is pid (process ID) and ppid (parent process ID).
###### how to get processes tree?
using `pstree` command:
```bash
pstree
```
###### more details of running processes (to see ppid):
use `-l` tag:
```bash
ps -l
```
###### how to see all running processes (for all users and terminals) with full details?
use `-efl` tag with `ps` command:
```bash
ps -efl
```
###### how to get live version of running processes?
using `top` command:
```bash
top
```
also you can download and use `htop` command.
###### how to execute command in the background?
by adding & at the end of the command
```bash
sleep 10 && echo "after sleeping for 10 seconds" &
# result: [1] 6235, [1] job ID, 6235 is the process ID
```
###### how to see jobs running in the background?
using `jobs` command:
```bash
jobs
```
###### if a process takes time and you want to make it run in the background:
1. press (Ctrl + z), this will pause it and put it in the jobs list
2. use `bg %jobID`  to resume it in the background (or `fg` to resume in the main bash)
###### how to kill a process?
using `kill` command, it send a kill signal to process, not actually killing it.
also we have to add one of these tags:
1. SIGHUB(1): restart the process with same process id.
2. SIGINT(2): it sends Ctrl+c which it stops the process and return the result.
3. SIGTERM(15): it will kill the process in a graceful way (delete all the child process).
4. SIGKILL(9): it will kill the process ungracefully.
each one of these tags has a number (between braces).
```bash
kill -<one of the signals> <process ID>
```
###### how to kill multiple processes for same app?
using `killall` command with signal and  redundant process name.
