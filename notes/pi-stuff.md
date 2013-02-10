Modifications
---

Enabling the UART port
---

    $ sudo vi /boot/cmdline.txt

replace

    dwc_otg.lpm_enable=0 console=ttyAMA0,115200 kgdboc=ttyAMA0,115200 console=tty1 $

with

    dwc_otg.lpm_enable=0 console=tty1 $

comment out /etc/inittab

    T0:23:respawn:/sbin/getty -L ttyAMA0 115200 vt100

reboot


Getting the system's MAC address
---

    ifconfig eth0 | grep -o -E '([[:xdigit:]]{1,2}:){5}[[:xdigit:]]{1,2}'


