# 1/ Install mysqldb 5.7.30 + phpmyadmin Standalone

### database modified for atlassian software
```
docker volume create --name mysqlvolume

docker run --name atlassian-mysqldb --restart unless-stopped -v mysqlvolume:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=your_strong_password -p 6306:3306 -d andromeda9096/mysqldb:5.7.30
```
#### note
mysql url= hostip:6306


### for manage mysqldb
```
docker run --name phpmyadmin --restart unless-stopped -d -e PMA_HOST=yourdatabase_server_ip -e PMA_PORT=6306 -p 8080:80 phpmyadmin
```

# 2/ Install mysqldb 5.7.30 + phpmyadmin using docker-compose
- clone this repos
- run docker-compose up -d

# 3/ Config database on your  Web-Browser
### phpmyadmin

http:host_ip:8080

user:root

pass: your_strong_password

