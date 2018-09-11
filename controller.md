---
layout: pages
---

# Raspberry Pi Setup

See [wiki](https://github.com/ut/INTPRN/wiki) for OS installation on your Raspi with [Raspian](https://www.raspbian.org/).

Start your Raspi, login via desktop or remote via SSH with default user Pi with password

```
 raspberry
```

Change the default password after first login and note it somewhere!

Initial configuration after first run:

* Set Timezone
* Setup internet connection (via WLAN oder Ethernet)
* Install Updates


## Install CUPS

```
    $ sudo apt-get install libcups2
    $ sudo apt-get install libcups2-dev libcupsimage2-dev git build-essential cups system-config-printer
    // start CUPS
    $ sudo /etc/init.d/cups start
```

You can reach the CUPS Webinterface via http://localhost:361

To allow your pi user to add printers:

```
    $ sudo usermod -aG lpadmin pi
    $ sudo service cups restart
```



## Install SQLite3

```
    sudo apt-get install sqlite3 ruby-sqlite3 libsqlite3-dev
```



    

## [Optional] Install ZJ-58 CUPS filter 

If you use a ZJ-58 thermal printer via USB, you need to install the CUPS filter via [github.com/klirichek/zj-58](https://github.com/klirichek/zj-58), since the built-in filter does not work! (Of course you can use any other printer, that is installed/accessible with your system)

```
    $ git clone https://github.com/klirichek/zj-58.git
    $ cd zj-58
    $ make
    $ sudo ./install
```

Then go to CUPS at https://localhost:631/ + select "Adding Printers and Classes", then "Printers: Add Printer" and add printer connected via "usb://Unknown/Printer".

To allow the Raspeberry default user "pi" to access the CUPS admin features:

```
    $ sudo usermod -aG lpadmin pi
    $ sudo service cups restart
```

See [scruss.com/blog/2015/07/12/thermal-printer-driver-for-cups-linux-and-raspberry-pi-zj-58](http://scruss.com/blog/2015/07/12/thermal-printer-driver-for-cups-linux-and-raspberry-pi-zj-58/) for a detailed description.


## Assemble the hardware

[Put together the pushputton on a breadboard](hardware.html) to trigger the printer

## Install PRNSTN script

PRNSTN is the script that turns this setup into an internet printing station.

See [github.com/ut/PRNSTN](https://github.com/ut/PRNSTN) for a description of the installation and usage.




