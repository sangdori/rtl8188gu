
Driver for Linux RTL8188GU (RTL8710B) (VID:PID = 0x0BDA:0xB711)
===============================================================

Is not original driver from Realtek, is build from source code from others official Realtek drivers.

Compiling & Building
--------------------
### Dependencies
To compile the driver, you need to have make and a compiler installed. In addition,
you must have the kernel headers installed. If you do not understand what this means,
consult your distro.
### Compiling

> make

### Installing

> sudo make install

### Disable CDROM mode and select in WiFi mode.

Open and edit usb_modeswitch.rules
> sudo vi /lib/udev/rules.d/40-usb_modeswitch.rules

Add as below
> ATTR{idVendor}=="0bda", ATTR{idProduct}=="1a2b", RUN+="/usr/sbin/usb_modeswitch -K -v 0bda -p 1a2b"

### Known problems

1. Very slow upload speed.
2. Problem reconnect from KNetworkManager in Kubuntu 20.04.
3. In Ubuntu 20.04 detected as GSM modem, need remove option driver as "sudo rmmod option".

### Testing
I tested on Ubuntu 16.04, 20.04 and last version OpenWRT, it's work...
