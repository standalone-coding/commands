```sh
# Export DB
mysqldump -u USER -pPASSWORD --routines DATABASE > BACKUP-FILE-NAME.sql
# Compress Export
sudo mysqldump -u USER -pPASSWORD --routines DATABASE | gzip > BACKUP-FILE-NAME.sql.gz
# Import DB
mysql -u USER -pPASSWORD DATABASE < BACKUP-FILE-NAME.sql
# Compress Import 
gunzip < [compressed_filename.sql.gz]  | mysql -u [user] -p[password] [databasename]
# mysql user permission
sudo chown -R mysql /var/lib/mysql
sudo chgrp -R mysql /var/lib/mysql
sudo chmod 755 /var/lib/mysql
```
For your databases, you can use the below code:
SET collation_connection = 'utf8_general_ci';
ALTER DATABASE your_database_name CHARACTER SET utf8 COLLATE utf8_general_ci;
ALTER TABLE your_table_name CONVERT TO CHARACTER SET utf8 COLLATE utf8_general_ci;

Create duplicate table:
CREATE TABLE DB.TABLE LIKE DB.TABLE;

### Test remote connection
```sh
mysql -u USER -pPASSWORD -h IP -P PORT -D DATABASE
```
### Set timezone
```mysql
SET GLOBAL time_zone = '+5:30';
SELECT now();
```