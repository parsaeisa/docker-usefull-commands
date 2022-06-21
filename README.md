# docker-usefull-commands

This is the place where I put docker commands which are usefull at least for me . 
I hope this repo would help you !!

## Mysql 
```bash 
sudo docker run -d -e MYSQL_ROOT_PASSWORD=root -p 3306:3306 -p 3307:3306 mariadb:10.2.14
```

## Msssql 
```bash 
docker run -e 'ACCEPT_EULA=Y' -e "SA_PASSWORD=Pass123!" -p 1433:1433 --name sqlserver -d mcr.microsoft.com/mssql/server:latest
/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'Pass123!' -i q1.sql 
```

## Open telemetry 
