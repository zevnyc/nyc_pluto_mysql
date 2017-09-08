# nyc_pluto_mysql
Load NYC PLUTO dataset into MySQL database

- Download PLUTO release 16v2 from http://www1.nyc.gov/site/planning/data-maps/open-data/dwn-pluto-mappluto.page
- Unzip it. It'll create folder nyc_pluto_16v2.
- Clone this project within folder nyc_pluto_16v2.
- Create a MySQL database (Assumption: You have a MySQL database user that can create a database).
```
create database nyc;
use nyc;
```
- Run the script that creates database objects and loads them from the csv files.
```
mysql -h <host> -u <mysql_user> -p<mysql_pwd> -D nyc --verbose < pluto_16v2_load.sql 
```

- (optional) Run the script that creates a couple of indexes on BBL. Additional indexes are needed depending on the usage.
```
mysql -h <host> -u <mysql_user> -p<mysql_pwd> -D nyc --verbose < pluto_16v2_indexes.sql 
```



