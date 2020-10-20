# nginx
```sh
sudo apt-get update
sudo apt install nginx
sudo systemctl status nginx
sudo systemctl restart nginx
```
---
# apache2
```
sudo apt-get update && upgrade
sudo apt-get install apache2
systemctl restart apache2
systemctl enable apache2
```
---
# PHP
```
sudo apt-get update
sudo add-apt-repository ppa:ondrej/php
sudo apt-get install -y php5.6
```
---
# mysql
```
sudo apt-get install mysql-server
USE mysql;
UPDATE user SET authentication_string=PASSWORD('password') WHERE User='root';
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
UPDATE user SET plugin="mysql_native_password" WHERE User='root';
CREATE USER 'dev'@'%' IDENTIFIED BY 'password';
GRANT ALL ON *.* TO 'dev'@'%';
FLUSH PRIVILEGES;
UPDATE user SET authentication_string=PASSWORD("password") WHERE User='root';
ALTER USER dev IDENTIFIED WITH mysql_native_password BY 'password';
```
---
# mysql 8
```
wget -c https://dev.mysql.com/get/mysql-apt-config_0.8.11-1_all.deb
sudo dpkg -i mysql-apt-config_0.8.11-1_all.deb
sudo apt-get update
sudo apt-get install mysql-server
sudo mysql_secure_installation
sudo service mysql stop
sudo service mysql start
```
***config***
>/etc/mysql/mysql.cnf
[client]
default-character-set=utf8

>[mysql]
default-character-set=utf8

>[mysqld]
collation-server = utf8_unicode_ci
character-set-server = utf8
default-authentication-plugin=mysql_native_password

==Uninstall MySQL 8==
```
sudo apt-get remove --purge mysql-server mysql-client mysql-common
sudo apt-get remove mysql-community-client-core
sudo apt-get remove mysql-community-server-core
sudo apt-get purge mysql-server mysql-client mysql-common mysql-server-core-* mysql-client-core-*
sudo apt-get autoremove
sudo apt-get autoclean
sudo rm -rf /etc/mysql /var/lib/mysql
```
==Uninstall MySQL 5==
```
sudo apt-get purge mysql*
sudo apt-get autoremove
sudo apt-get autoclean
```
---

# PhpMyAdmin
```
sudo apt-get install -y phpmyadmin php5.6-mbstring php5.6-gettext php5.6-mysqli
sudo service apache2 restart
```
---
# Update NodeJS
```sh
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt-get install -y nodejs
```
---
# Redis
```
sudo apt-get install redis-server
sudo systemctl enable redis-server.service
```
---
# SSL
[Certbot](https://certbot.eff.org/lets-encrypt/ubuntubionic-apache)
```
sudo apt-get install snapd
sudo apt-get remove certbot
sudo dnf remove certbot
sudo yum remove certbot
sudo snap install --classic certbot
sudo certbot --nginx --register-unsafely-without-email
sudo certbot renew --dry-run
```
# Service
```
/etc/init.d/ssh start/stop/restart.
```
