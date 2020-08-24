Download and install Raspbian Buster Lite
```bash
Sudo passwd root
```
(change your root password)

```bash
Sudo apt-get update
Sudo apt-get install xfe 
Sudo apt-get install xfce4 
Sudo apt-get update
Sudo apt-get install libwebkitgtk-1.0-0
Sudo apt-get install iceweasel 
Sudo apt-get install chromium
```
xfe - gui
xfce4 - file manager
iceweasel - firefox (really only needed for the Citrix certificate)
chromium - chrome

```bash
sudo raspi-config
```
Select Boot Options, Desktop/CLI, and select Desktop or Desktop Autologin.

https://www.citrix.com/en-gb/downloads/workspace-app/linux/workspace-app-for-linux-latest.html
```bash
Sudo dpkg -i icaclient_20.06.0.15_armhf.deb (download from citrix)
```

