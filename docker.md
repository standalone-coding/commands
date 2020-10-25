```sh
docker exec -it my-mysql bash -l
docker run --detach --name=test-mysql -p 52000:3306  --env="MYSQL_ROOT_PASSWORD=mypassword" mysql
docker run --name my-mysql --env MYSQL_ROOT_PASSWORD=123456 --env USER=dev -d -p 1000:3307 mysql:8.0.1

docker run --name my-mysql -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_TCP_PORT=3307 -e USER=root -d mysql:8.0.1
docker run --name my-mysql -e MYSQL_TCP_PORT=3307 MYSQL_ROOT_PASSWORD=123456 -d mysql:8.0.1
docker run --name my-own-phpmyadmin -d --link my-mysql:db -p 8081:80 phpmyadmin/phpmyadmin
```