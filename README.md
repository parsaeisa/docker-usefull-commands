# docker-usefull-commands

This is the place where I put docker commands which are usefull at least for me . 
I hope this repo would help you !!

## Mysql 
```bash 
sudo docker run -d -e MYSQL_ROOT_PASSWORD=root -p 3306:3306 -p 3307:3306 mariadb:10.2.14
```

## Mssql 
```bash 
docker run -e 'ACCEPT_EULA=Y' -e "SA_PASSWORD=Pass123!" -p 1433:1433 --name sqlserver -d mcr.microsoft.com/mssql/server:latest
/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'Pass123!' -i q1.sql 
```

* You can name your container with --name parameter while running the image . This can help you to interact more easily with containers . 

## Interacting with containers 
### Copy file in container 
``` bash 
sudo docker cp db.sql <container id>:/
```
### Go to container terminal 
```bash 
sudo docker exec -it <container id> bash
```

* You can get container Id from docker ps command .

## Open telemetry 
```bash 
 docker run --name jaeger \
  -e COLLECTOR_ZIPKIN_HOST_PORT=:9411 \
  -p 5775:5775/udp \
  -p 6831:6831/udp \
  -p 6832:6832/udp \
  -p 5778:5778 \
  -p 16686:16686 \
  -p 14250:14250 \
  -p 14268:14268 \
  -p 14269:14269 \
  -p 9411:9411 \
  jaegertracing/all-in-one:1.29
```

jeager runs on http://127.0.0.1:16686/ .
