# docker_chisel

```
cd /Users/i830671/Documents/XSA/docker_mysqlc
docker build --no-cache -t alunde/mysqlc:latest .
docker build -t alunde/mysqlc:latest .
echo "docker run -ti -p 3306:3306 alunde/mysqlc:latest"
docker push alunde/mysqlc:latest
cf delete mysqlc -f -r
cf push mysqlc --docker-image alunde/mysqlc:latest -m 640M -k 2G --no-route --no-start -u none
cf enable-ssh mysqlc
cf restart mysqlc
cf ssh mysqlc
```
Once you are shelled into the container, you can access the MySQL Sever through the Chisel Tunnel with this.
```
/usr/bin/mysql -u root -p -h 127.0.0.1 -P 3306 -D test -e "SELECT * FROM test.test2;"
Enter password: Nirvana8484
+----+----------+
| id | value    |
+----+----------+
|  1 | One      |
|  2 | Two      |
|  3 | Thareee! |
+----+----------+
```
