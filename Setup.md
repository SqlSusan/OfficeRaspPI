Download and install Raspbian Buster Lite
https://www.raspberrypi.org/downloads/raspberry-pi-os/

(change your root password)
```bash
sudo passwd root
```

Install dependant applications

- xfe (gui)
- xfce4 (file manager)
- iceweasel (firefox (really only needed for the Citrix certificate))
- chromium (chrome)
```bash
sudo apt-get update
sudo apt-get install xfe 
sudo apt-get install xfce4 
sudo apt-get install libwebkitgtk-1.0-0
sudo apt-get install iceweasel 
sudo apt-get install chromium
sudo apt-get update
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

When loaded into the desktop UI, with some monitors you may notice a black border. To correct this, open pi config

```bash
sudo nano /boot/config.txt
```

Here you might need to experiment with what works best on your screens:
```bash
# uncomment this if your display has a black border of unused pixels visible
# and your display can output without overscan
disable_overscan=1
```

If this settings doesn't work, comment disable_overscan out again, then try adjusting these settings:
```bash
# uncomment the following to adjust overscan. Use positive numbers if console
# goes off screen, and negative if there is too much border
overscan_left=-50
overscan_right=-50
overscan_top=-50
overscan_bottom=-50
```

Download the Citrix workspace client and install (this has receiver built in)
https://www.citrix.com/en-gb/downloads/workspace-app/linux/workspace-app-for-linux-latest.html
```bash
sudo dpkg -i icaclient_20.06.0.15_armhf.deb 
```

Copy the root certificate from the Firefox CA store to the Citrix ICA client store.
```bash
sudo cp /usr/share/ca-certificates/mozilla/Entrust_Root_Certication_Authority_-_G2.crt /opt/Citrix/ICAClient/keystore/cacerts/
```

Log into Citrix in Chromium, in settings at the top right, click "Change Citrix Receiver...". Click "Use Full Version".

## Smoothing out YouTube

There are a couple of methods to do this. The easiest is to install this extension in Chromium:

[h264ify](https://chrome.google.com/webstore/detail/h264ify/aleakchihdccplidncghkekgioiakgal/related?hl=en)



## Optional - install bluetooth audio packages

``` bash
#!/bin/bash

# Add some audio and Bluetooth packages
apt-get install blueman pulseaudio pavucontrol pulseaudio-module-bluetooth
echo
echo
read -p 'Say "ALEXA PAIR" and then press ENTER to continue'
echo
echo

# Capture Mac Address of Alexa Speaker by grepping for the string "Echo" from the bluetoothctl scan:
ALEXAMACADDRESS=$(sudo timeout 10s bluetoothctl scan on >> /home/pi/scan-output.txt | cat /home/pi/scan-output.txt | grep -m1 '.*Echo.*' | awk '{print $3}')

bluetoothctl pair $ALEXAMACADDRESS
bluetoothctl connect $ALEXAMACADDRESS
bluetoothctl trust $ALEXAMACADDRESS
```

