Ultimarc-linux
==============

Library and command line utility 

This fork uses cmake to build it

#### Introduction:
This utility will configure the following Ultimarc boards; ServoStik, PACDrive, IPAC Ultimate, I-Pac 2, I-Pac 4, Mini-Pac, JPAC, UltraStik 360, PacLED64, U-HID and U-HID Nano.  There is support for the PAC 2015 boards, UltraStik 2015 board and the previous generation of the PAC boards.  It uses json configuration files to configure the different boards.  It also supports the ability to change the device ID of the UltraStik 360 boards.  Allowing for the configuring of four different boards at once.

This library and command line utility support 2012 through 2015 boards.  If you need support for older Ultimarc boards, please look at the following utility developed by Travis, <a href='http://www.zumbrovalley.net/articles.php?catid=3'>Ipacutil</a> or use the Windows WinIpac v1 from <a href='http://www.ultimarc.com'>Ultimarc</a>

#### Required Libraries
To build this tool the following libraries need to be install on your system.
* libudev-dev
* json-c (0.11), <a href='https://github.com/json-c/json-c/wiki'>site</a>
* libusb-1.0 (1.0.18), <a href='http://libusb.info'>site</a>
* libtool

#### UDEV Rule:
This utility requires folder permission changes to the usb device directories before it can do the configuration changes to the boards.  The udev rule in the base directory named 21-ultimarc.rules needs to be placed in /etc/udev/rules.d directory.  Placing the file in that directory usually requires root permissions.


#### Building Utility:
To build this project, create a build folder and run

```
cd src
mkdir build
cd build
cmake ..
make
```

The executable will be in src/build directory and named umtool.
* ./umtool ../src/ipac2.json

#### Donations:
<a href='https://paypal.me/snowywhitewater?locale.x=en_US'>Click here to lend your support through PayPal!</a>
