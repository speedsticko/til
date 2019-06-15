Single Board Computer

Connecting a PI to a Computer with just an ethernet
=====
You can go headless and connect a PI directly to your computer over ethernet with a "local-link" by using the hostname: "raspberrypi.local". You can also connect it to your router.
Make sure ssh is first enabled either using "sudo raspi-config" or the "ssh" file in /boot. Username is: pi
Reference https://raspberrypi.stackexchange.com/questions/37920/how-do-i-set-up-networking-wifi-static-ip-address/37921#37921

Using an external SSD
-----
The PI can't supply too much power through the USB ports so better to have a self-powered drive. The Samsung T5 drives seem to be able to be get enough power as long as nothing else is drawing power. USB3 will fall back to USB2.

Harddrive Formats
----
Most USB devices will be ExFAT so that it is compatible with the most broad range of devices (Windows, Linux, MacOS, Android). 
Ext4 is the native file format. https://www.raspberrypi.org/documentation/configuration/external-storage.md

MySQL (MariaDB) on RaspberryPI
----
When you connect locally you will need to use "sudo mysql -u root" since you need to have the root user's PID when connecting locally.
To move the datadir to the external drive:
- Create and mount a new datadir
- Create a new configuration file at /etc/mysql/mariadb.conf.d/99-local.cnf with:
[mysql]
datadir = /mnt/externalssd/mysql-datadir
- Stop mysql: sudo service mysql stop
- Copy the previous /var/lib/mysql to the new datadir. The previous datadir was defined in the 50-server.cnf file.

- Make sure the permissions on the new datadir are correct and are owned by mysql:mysql
```
/var/lib/mysql (drwx——-)
/var/lilb/mysql/mysql (drwx——)
files in this folder should be (rw-rw—-)
Same for all databases folders
Owner /var/lib
# chown -R mysql.mysql mysql
```
- Restart the mysql service: sudo service mysql start
