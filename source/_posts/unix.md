---
title: unix
date: 2016-04-29 09:26:13
tags: unix
---

ufw

sudo apt-get install ufw

sudo ufw enable
sudo ufw allow ssh
sudo ufw allow 22
sudo ufw allow http
sudo ufw allow https
sudo ufw allow 3000

sudo ufw deny http

sudo ufw status




$ vi /etc/ssh/sshd_config

PermitRootLogin no
PubkeyAuthentication no
AllowUsers ramesh john jason
Port 222


server timezone

sudo dpkg-reconfigure tzdata

Filter for brute-force interactive SSH logins
grep sshd.\*Failed /var/log/auth.log | less

Look for failed connections (i.e. no login attempted, could be a port scanner, etc.):
grep sshd.*Did /var/log/auth.log | less


sudo apt-get install fail2ban

/etc/apache2/pache2.conf
<Directory /var/www/>
    Options Indexes FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>

sudo a2enmod rewrite
sudo service apache2 restart