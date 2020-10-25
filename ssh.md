scp -C -i anonymous

chmod 400 ~/.ssh/id_rsa

ssh-keygen -C "anonymous"

ssh-copy-id -i luckyindia root@ip