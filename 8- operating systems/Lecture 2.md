#### copy files/dirs
```bash
cp <file source path> <file destination path>
```
##### open a file with vi text-editor
```bash
vi <filename>
```
vi has two modes: insert mode and command mode
command mode shortcuts:
- dd: delete the full raw
- wd: delete one word
- yy: copy line
- p: paste line
#### execute shell commands inside vi
we can execute bash/shell commands inside vi and results will be appended to text file
```vi
:.!ls
```
#### open shell inside vi:
```vi
:sh
```
![[vi_and_shell.png]]
#### Linux philosophy
1. Small is beautiful
2. Each program does one thing (only) and does it will
3. Prototype as soon as possible
4. Choose portability over efficiency
5. Store data in Flat text files
6. Use software leverage (لو في حاجة مسبقة الصنع استعملها ويتقاطع مع 3)
7. Use shell scripts to increase leverage and portability
8. Avoid captive use interfaces
9. Make every program a filter
