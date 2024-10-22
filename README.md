# Bassic Configurasi Debian

# Configurasi IP
- nano /etc/network/interfaces
- /etc/init.d/networking restart


# Configurasi DHCP
- apt-cdrom add
- apt-get install isc-dhcp-server
- nano /etc/dhcp/dhcpd.conf
- nano /etc/default/isc-dhcp-server
- service isc-dhcp-server


# Configurasi SSH
  apt-cdrom add
    apt-get install ssh
      nano /etc/ssh/sshd_config


# Configurasi DNS
- apt-cdrom add
- apt-get install bind9
- cd /etc/bind
- > ls
- > cp db.127 db.192
- > cp db.local db.rama
- nano db.rama (___)
- nano db.192 (___)
- nano /etc/bind/named.conf.default-zones (___)
- nano /etc/resolv.conf (____)
- apt-cdrom add
- apt-get install resolv
- apt-cdrom add
- apt-get install dnsutils


# Configurasi Webserver
- apt-cdrom add
- apt-get install apache2 php
- cd /etc/apache2/sites-available/
- > ls
- cp 000-default.conf rama.conf
- nano rama.conf (ubah localhost nya saja menjadi dns: rama.com, dan jangan menambahkan nameserver baru)
- cd /var/www/html/
- > ls
- nano index.html
- cd /etc/apache2/sites-enabled/
- #a2ensite rama.conf
- a2dissite 000-default.conf (menonaktifkan direktori defaultnya)
- service apache2 restart
