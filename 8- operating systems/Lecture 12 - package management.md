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
###### how to see specific package references in the packages list?
```bash
dpkg -L <package file name>
```
###### how to remove package?
```bash
dpkg -r <package file name>
```
###### If I want the package name from its reference file name (opposite of -L)?
```bash
dpkg -S <package file name>
```
### APT
`apt` is helper tool for package manager to easily work with packages, it take care of packages dependencies, unpackaging the package and install it
```bash
sudo apt install nsnake
```
`apt` determine where to search for package by reading sources file (package sources list).
###### where to find the packages sources list?
at `/home/etc/apt`
###### how to update the packages dictionary list?
```bash
sudo apt update
```
###### how to update the packages?
```bash
sudo apt upgrade
```
###### difference between `apt` and `apt-get`?
same, but `apt-get` is more low level.
###### how to search if a package available?
```bash
sudo apt search <package name >
```
###### how to remove with apt?
```bash
sudo apt remove <package name>
```
## Universal Package Management:
there are many of them, the main are:
1. `snap` which is the main store on Ubuntu
2. `flatpack` 
3. `AppImage`
