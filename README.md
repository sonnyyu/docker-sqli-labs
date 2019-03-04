git clone https://github.com/sonnyyu/docker-sqli-labs

cd docker-sqli-labs

docker-compose up --build

docker exec -it sqli-labs /usr/bin/mysql -uroot -e "SET global log_output = 'FILE'; SET global general_log_file='/var/log/mysql/all.log'; SET global general_log = ON;"

curl http://10.145.88.192/sql-connections/setup-db.php

docker run -it --rm sonnyyu_sqlmap --url http://10.145.88.192/Less-1/?id=2

http://10.145.88.192:8000

admin/password

docker-compose stop

docker-compose down

docker container prune -f

docker image prune -a -f

docker volume prune -f

docker network prune -f

docker system prune -f

sudo rm -rf /var/lib/docker/volumes/*

docker-compose up -d
