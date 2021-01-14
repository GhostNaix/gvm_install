# gvm_install
A script to install GVM / OpenVAS 11 or 20 on Ubuntu 20.04

## Note
If you get an error at login during the login some where along the lines off `The Greenbone Vulnerability Manager service is not responding` reboot the host or start the restart the `gvm` service via:
```
service gvm start
```
or 
```
systemctl start gvm
```

Usage:

Ubuntu:
```
wget https://raw.githubusercontent.com/GhostNaix/gvm_install/master/install_gvm.sh
chmod +x install_gvm.sh
sudo ./install_gvm.sh 
```

Debian:
* Note, I had an issue when testing GVM version 20 on Debian where nmap wasn't detected. I don't have a resolution for this at the moment so if you select version 20 on Debian stable you may run into issues. If you have any idea how to fix this please let me know. 
```
apt install sudo
usermod -aG sudo <your-user-name> # add your user to the sudoer's group
wget https://raw.githubusercontent.com/GhostNaix/gvm_install/master/install_gvm.sh
chmod +x install_gvm.sh
sudo -i
./install_gvm.sh
```

When the script completes if everything went well the web interface should be available on the machine you ran this on. 
Locate the IP address `ip a` is one way to do that. Then, point a web browser to `https://<ip-address-of-machine>:9392` where `<ip-address-of-machine>`
is the actual address.

It uses a self-signed certificate so you'll see a warning in the web browser about that. Feel free to replace the cert or ignore the warning.


Depending on how your network is set up--specifically, with regards to IPv4 and IPv6--you may run into issues accessing the web interface. See <a href=https://github.com/yu210148/gvm_install/issues/7>Issue #7</a> for more info. 

Based on [koromicha's excellent guide](https://kifarunix.com/install-and-setup-gvm-11-on-ubuntu-20-04/). Thanks to the commenters there as well for useful troubleshooting info.

Takes a while to do everything (a couple of hours on my last test).

Tested successfully in VMs in December of 2020. Your experience may be different. Use at your own risk.



Licensed under GPLv3 or later.
