sudo apt-get install phpmyadmin php5.6-mbstring php5.6-gettext
sudo service apache2 restart

sudo dpkg-reconfigure phpmyadmin

sudo apt-get -f install
sudo dpkg -P phpmyadmin  
sudo rm -vf /etc/apache2/conf.d/phpmyadmin.conf
sudo rm -vfR /usr/share/phpmyadmin
sudo service apache2 restart
sudo apt-get autoremove phpmyadmin


$cfg['SendErrorReports'] = 'never';