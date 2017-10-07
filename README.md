
# SETUP

```shell
scp isu:isucon5q.sql.gz ./
mysql -u root -p -e create database isucon5q
gzcat isucon5q.sql.gz | mysql -u root -p isucon5q
make
./app
open http://localhost:8080/
```

