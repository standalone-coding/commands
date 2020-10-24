### Port forwarding for apache2
```
location ~* \.php$ {
 	proxy_pass http://127.0.0.1:81;
 	proxy_set_header Host $host;
 	proxy_set_header X-Real-IP $remote_addr;
 	proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
 	proxy_set_header X-Forwarded-Proto $scheme;
}
```
### Enable php-fpm
```sh
# Install PHP
sudo apt-get install php7.4 php7.4-cli php7.4-fpm

# Configure PHP-fpm for Nginx
sudo nano /etc/php/7.4/fpm/pool.d/www.conf
```
> listen= /var/run/php/php7.4-fpm.sock
```sh
sudo nano /etc/php/7.3/fpm/php.ini
```
> ;cgi.fix_pathinfo=1 -> cgi.fix_pathinfo=0
```sh
# Start PHP-fpm service
sudo service php7.4-fpm start
```
```sh
sudo nano /etc/nginx/sites-available/default
```
```
location ~* \.php$ {
 	fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
 	include fastcgi_params;
 	fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
 	fastcgi_param SCRIPT_NAME $fastcgi_script_name;
}
```
### Test nginx config
```sh
sudo nginx -t
```
