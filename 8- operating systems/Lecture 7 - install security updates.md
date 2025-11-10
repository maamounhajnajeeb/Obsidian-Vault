1. First, ensure your package list is up to date by running:
```bash
sudo apt update
```
This downloads the latest package information from the configured repositories, including the security pocket where updates are published.

2. To view a list of available security updates, use:
```bash
sudo apt list --upgradable | grep -i security
```
This command filters the list of upgradable packages to show only those related to security updates.

3. **Alternatively**, you can use this command to see only the security-related packages that would be installed during an upgrade:
```bash
sudo apt-get -s dist-upgrade | grep "^Inst" | grep -i security
```

4. To install only security updates, you can use this command to identify security updates and installs them without affecting non-security packages:
```bash
sudo apt-get -s dist-upgrade | grep "^Inst" | grep -i security | awk -F " " '{print $2}' | xargs sudo apt-get install -y
```
