## tr command
transformation command which takes stream of text not file.
examples:
1. delete char
```bash
echo "This iss a test 123 !" | tr -d 's'
result: Thi i a tet 123 !
```
2. switch char with another one
```bash
echo "This iss a test 123 !" | tr [i] [I]
result: ThIs Iss a test 123 !
```
3. clear redundancy
```bash
echo "This iss a test 123 !" | tr -s 's'
result: This Is a test 123 !
```
4. from lower to upper
```bash
echo "This iss a test 123 !" | tr [a-z] [A-Z]
result: This Is a test 123 !
```
5. delete digits from text stream
```bash
echo "This iss a test 123 !" | tr -d [:digits:]
result: This Is a test !
```
6. assign file as stream of text then use tr with it
```bash
cat /etc/home | tr [:lower:] [:upper:]
```
## cut command
1. get first char
```bash
"This is string of chars" | cut -c 1
```
2. get first char, and any other char
```bash
"This is string of chars" | cut -c 1,20
```
3. get sequence of chars, with another char
```bash
"This is string of chars" | cut -c 1-20,22
```
4. split into fields and fetch any of these fields
```bash
cat /etc/passwd | cut -f 1,3 -d ":"
```
