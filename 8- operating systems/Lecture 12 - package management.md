###### how to see all packages?
```bash
dpkg -l
```
###### how to see package properties?
```bash
dpkg -p <package name like: bash>
```
###### how to see downloaded (not-installed) package properties?
```bash
dpkg -I <package file name>
```
###### how to install downloaded package?
```bash
sudo dpkg -i <package file name>
```
