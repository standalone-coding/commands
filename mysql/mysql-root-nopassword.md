#### step 1

Stop the mysql demon with this command

```sh
sudo /etc/init.d/mysql stop
```

#### step 2

Start the mysql demon process with following

```sh
sudo /usr/sbin/mysqld --skip-grant-tables --skip-networking &
```
> (at this point it's safest to disable networking)

#### step 3

Start the mysql client with
```sh
mysql -u root
```

#### step 4

Then run following in mysql prompt, so you are able to change any password

```sh
FLUSH PRIVILEGES;
```
#### step 5

Then reset password with

```sh
SET PASSWORD FOR root@'localhost' = PASSWORD('password');
```

#### step 6

In case you happen to have a mysql root account that can connect from everywhere, this is recommended

```sh
UPDATE mysql.user SET Password=PASSWORD('newpwd') WHERE User='root';
```

#### step 7

Once you receive a message indicating a succesful query, then run

```sh
FLUSH PRIVILEGES;
```
#### step 8

Stop mysql and relaunch it with

```sh
sudo /etc/init.d/mysql stop
sudo /etc/init.d/mysql start
```