CC3200 Linux ARM/X86 flash tool
================================================================================
>**Note:**

> - This document contains a HOWTO on flash applications for the TI CC3200
Launchpad under Ubuntu 64bit 14.04.

> - Libs and tools are extracted from Energia. The hardware is tested on CC3200-LAUNCHXL
And additionally we test flashing from BBB debian(Not released yet). Courtesy of robertinant

Setup
---------------------
![BBB+CC3200](https://github.com/sheenhx/cc3200sdk/tools/energia-0101E0017/BBB.jpg "BBB+CC3200")

Remove all the SOP2 jumpers and connect J8 like shown in picture above.
In this way we dont' have to remove any jumper when we flash images from BBB or Ubuntu 64bits.

Flash your example
---------------------

Before that you should enumerate the device as /dev/ttyUSB1 

```
debian@beaglebone:~/github$ cat /etc/debian_version 
7.9
debian@beaglebone:~/github$ uname -a
Linux beaglebone 3.8.13-bone70 #1 SMP Fri Jan 23 02:15:42 UTC 2015 armv7l GNU/Linux
debian@beaglebone:~/github/cc3200prog$ sudo ./cc3200prog /dev/ttyUSB1 ~/WiFiWebClientRepeating.cpp.bin 
Open UART /dev/ttyUSB1
open UART success
Triggering bootloader....
Getting storage list
Bootloader Version: 4
Silicon version ES1.32 or higher
Bootloader version is 2, 1, 4, 0
It's a CC3200 device: PG1.33 or higher
Switch UART pinmux to APPS
Switch to NWP bootloader complete
Load common boot command for PG1.33 or higher
Bootloader version is 2, 0, 4, 0
BlockSize is 4096, number of blocks is 16
erasing 13 blocks starting from  0
erasing file "/sys/mcuimg.bin"
deleting file "/sys/mcuimg.bin"
erase file completed
Downloading file "/sys/mcuimg.bin" with size 23952
......
Download complete
```

After it is completed, the program will automatically run.
