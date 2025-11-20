## File Types:
- How to know the type of file?
```bash
ls -lh

drwxr-xr-x  3 maamoun-haj-najeeb maamoun-haj-najeeb 4.0K Nov 18 20:22 Desktop
```
`d` stands for directory.
- type of file:
```bash
$ file config.docker-template.php
config.docker-template.php: PHP script, ASCII text
```
### Less and more commands
- show file
```bash
more <file name>
less <file name>
```
- first lines of file content:
```
head <file name>
```
- last lines of file content:
```
tail <file name>
```
### Deleting files and folders:
using `rm` command:
```bash
rm <file name>
```
use `-r` with folders:
```bash
rm <folder name> -r
```
## Finding Files:
### find command:
very powerful command, it use brute force to find files.
examples:
```bash
find . -type f -name d*.log
# . -> searching location
# f -> type which is file
# d*.log -> name of the file, or something like it
#           we can use d??.log or *.log
```
### how to make an operation after finding file?
we can assume that find output is variable and pipe its results to another command, example:
```bash
cat $(find . -type f -name d??.log) | grep Error
```
### how to make more than one operation on files and folders?
```bash
ls file? | xargs -I {} mkdir {}.d
```
## Files Archive:
- Archiving in Linux has three options:
	1. archiving (make all files as one file)
	2. compression
	3. both
- to archive files, use `tar` command (tape archive):
```bash
tar -cvf apps_packages.tar apps_packages # add / if you want to archive a directory
```
- how to see content of archive file:
```bash
tar -tf <archived file name>
```
- how to extract files from tar files:
```bash
tar -xvf <archived file name> # if you want to change execution path use -C tag
```
#### Compression:
- using `gzip`:
```bash
gzip <file name>
```
- compress without deleting original file using `-k` tag:
```bash
gzip -k <file name>
```
- to decompress files use `-d` tag (d for decompress):
```bash
gzip -d <compressed file>
```
