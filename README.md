# Bassic Configurasi Debian


### Configurasi Network Interface
1. Edit the network interface file:
```bash
nano /etc/network/interfaces
```
2. Restart networking service:
```bash
/etc/init.d/networking restart
```
#


### Configurasi DHCP
1. Add installation media (if required):
```bash
apt-cdrom add
```
2.  Install DHCP server:
```bash
apt-get install isc-dhcp-server
```
3. Edit DHCP configuration file:
```bash
nano /etc/dhcp/dhcpd.conf
```
4. Set the default configuration for DHCP server:
```bash
nano /etc/default/isc-dhcp-server
```
5. Start the DHCP server service:
```bash
service isc-dhcp-server
```
#


### Configurasi SSH
1. Add installation media (if required):
```bash
apt-cdrom add
```
2. Install SSH:
```bash
apt-get install ssh
```
3. Edit SSH configuration file:
```bash
nano /etc/ssh/sshd_config
```
#


### Configurasi DNS
1. Add installation media (if required):
```bash
apt-cdrom add
```
2. Install BIND9:
```bash
apt-get install bind9
```
3. Navigate to the BIND configuration directory:
```bash
cd /etc/bind
```
4. List the files to check contents:
```bash
> ls
```
5. Copy DNS database files:
```bash
> cp db.127 db.192
> cp db.local db.rama
```
6. Edit the DNS zone files:
```bash
nano db.rama (___)
nano db.192 (___)
```
7. Update the default zone configuration:
```bash
nano /etc/bind/named.conf.default-zones (___)
```
8. Update the default zone configuration:
```bash
nano /etc/resolv.conf (____)
```
9. Add installation media (if required):
```bash
apt-cdrom add
```
10. Install DNS resolver package:
```bash
apt-get install resolv
```
11. Add installation media again (if required):
```bash
apt-cdrom add
```
12. Install DNS utilities package
```bash
apt-get install dnsutils
```
#


### Configurasi Webserver
1. Add installation media (if required):
```bash
apt-cdrom add
```
2. Install Apache and PHP:
```bash
apt-get install apache2 php
```
3. Navigate to the Apache configuration directory:
```bash
cd /etc/apache2/sites-available/
```
4. List available configuration files
```bash
> ls
```
5. Copy the default configuration file to create a new virtual host configuration:
```bash
cp 000-default.conf rama.conf
```
6. Edit the configuration file (`rama.conf`)
   - Open the file
```bash
nano rama.conf (ubah localhost nya saja menjadi dns: rama.com, dan jangan menambahkan nameserver baru)
```
7. Navigate to the web root directory:
```bash
cd /var/www/html/
```
8. List files in the web root to verify content:
```bash
> ls
```
9. Edit the `index.html` file to customize the homepage (opsional): 
```bash
nano index.html
```
10. Go to the enabled sites directory:
```bash
cd /etc/apache2/sites-enabled/
```
11. Enable the new site (`rama.conf`):
```bash
#a2ensite rama.conf
```
12. Disable the default site (`000-default.conf`) to prevent conflicts:
```bash
a2dissite 000-default.conf (menonaktifkan direktori defaultnya)
```
13. Restart Apache to apply changes:
```bash
service apache2 restart
```
