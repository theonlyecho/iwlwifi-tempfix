# Manual WLAN Refresh Script
## IWLWIFI Driver Solution

THIS DRIVER SOLUTION WILL BE UNMAINTAINED AS OF 02-20-22 but should work fine as usual..

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

This is a temporary solution for Linux Users who are having trouble with reconnecting to access points with machine using iwlwifi driver.

## Features

- Auto unload wifi driver
- Auto restart network manager
- Restarts WLAN interface upon execution


I have tried to look for any solutions about this issue on iwlwifi driver where I can't reconnect
to Access points or wifi networks unless I force reboot my machine. I tried just restarting the interface itself but it is still unbable to reconnect. By unloading the driver, and had it load again the wlan interface was able to connect to any wifi networks which pushed me to create this small script. Feel free to open any issues or suggestions as need if I can help.



## Tech

- [Bash] - Just plain bash script for easy execution


## Installation


```sh
Check first your wireless adapter by using lspci command for linux You will be provided with a list of drivers but not their indexes/numbers : It will show like this:

01:00.1 Audio device: Advanced Micro Devices, Inc. [AMD/ATI] Turks HDMI Audio [Radeon HD 6500/6600 / 6700M Series]24:00.0 FireWire (IEEE 1394): JMicron Technology Corp. IEEE 1394 Host Controller (rev 30) 24:00.1 System peripheral: JMicron Technology Corp. SD/MMC Host Controller (rev 30) 24:00.2 SD Host controller: JMicron Technology Corp. Standard SD Host Controller (rev 30) 25:00.0 Network controller: Intel Corporation Centrino Advanced-N 6205 [Taylor Peak] (rev 34)`

My adapter shows as 25:00.0 so I need to find the correct indicator for the driver.

Type command cd /sys/bus/pci/devices and you will be provided by a list of numbers 0000:00:1d.0 0000:00:1f.2 0000:01:00.1 0000:24:00.1 0000:25:00.0

Find and copy the filename that corresponds to the pci device number For example : 25:00.0 Network controller , it will be 0000:25:00.0 Open and edit the file before executing

Make executable by chmod +x wifi-resetter

Run as sudo ./wifi-resetter on your terminal.
```


