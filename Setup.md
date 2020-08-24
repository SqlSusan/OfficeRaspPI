Download and install Raspbian Buster Lite
https://www.raspberrypi.org/downloads/raspberry-pi-os/

(change your root password)
```bash
Sudo passwd root
```

Install dependant applications
xfe - gui
xfce4 - file manager
iceweasel - firefox (really only needed for the Citrix certificate)
chromium - chrome
```bash
Sudo apt-get update
Sudo apt-get install xfe 
Sudo apt-get install xfce4 
Sudo apt-get update
Sudo apt-get install libwebkitgtk-1.0-0
Sudo apt-get install iceweasel 
Sudo apt-get install chromium
```

https://www.raspberrypi.org/forums/viewtopic.php?t=7571
Install slim as the login manager
```bash
sudo apt-get install slim
```

Change the boot options to load into the desktop
```bash
sudo raspi-config
```
Select Boot Options, Desktop/CLI, and select Desktop or Desktop Autologin.

Download the Citrix workspace client and install (this has receiver built in)
https://www.citrix.com/en-gb/downloads/workspace-app/linux/workspace-app-for-linux-latest.html
```bash
Sudo dpkg -i icaclient_20.06.0.15_armhf.deb 
```

Copy the root certificate from the Firefox CA store to the Citrix ICA client store.
```bash
sudo cp /usr/share/ca-certificates/mozilla/Entrust_Root_Certication_Authority_-_G2.crt /opt/Citrix/ICAClient/keystore/cacerts/
```

Log into Citrix in Chromium, in settings at the top right, click "Change Citrix Receiver...". Click "Use Full Version".
