docker run --name some-mysql \
-e MYSQL_ROOT_PASSWORD=password \
-v "$PWD"/conf.d:/etc/mysql/conf.d \
-v "$PWD"/mysql:/var/lib/mysql \
-p 3306:3306 \
-d mysql:5.7.15
docker exec -it $(docker ps | grep mysql | awk '{ print $1 }') /bin/bash
mysql -hlocalhost -P3306 -uroot -ppassword
use mysql;
