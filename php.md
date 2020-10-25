```sh
sudo apt-get update
sudo add-apt-repository ppa:ondrej/php
sudo apt-get install -y php5.6

#https://vitux.com/how-to-install-php5-and-php7-on-ubuntu-18-04-lts/
sudo apt-get install -y php5.6-curl
sudo apt-get install -y php5.6-redis
sudo apt-get install -y php5.6-mysqli

sudo update-alternatives --config php
sudo a2dismod php7.2
sudo a2enmod php7.1
sudo update-alternatives --set php /usr/bin/php7.1

```
ini_set('display_errors', 1);
ini_set('display_startup_errors', 1);
error_reporting(E_ALL);