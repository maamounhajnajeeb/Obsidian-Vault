---
tags:
  - python
  - package_managers
---
## working with UV on local computer

1. install UV
```shell
pip install uv
```

2. install dependencies
```shell
uv sync
```

3. check if uv is working
```shell
uv run main.py
```
and it should shows:
`Hello from tutor-package!`

4. run tutor via docker and tutor command:
```shell
uv run tutor local launch
```

5. to export package into requirements.txt file use this command:
```shell
uv pip compile pyproject.toml --output-file requirements.txt
```

6. add new package
```shell
uv add <package_name>
```  

### Good video resource:
[uv with arjan code](https://www.youtube.com/watch?v=qh98qOND6MI)
