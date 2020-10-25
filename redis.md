```sh
# background run
redis-server --port 6381 --daemonize yes

For windows:

Step 1: Install redis as a service

redis-server --server-install 
Step 2: Run background

redis-server --server-start

redis-server --daemonize yes

sudo apt-get install redis-server
sudo systemctl enable redis-server.service
sudo service redis-server restart

# bind ip
/etc/redis/redis.conf
bind 0.0.0.0 127.0.0.1