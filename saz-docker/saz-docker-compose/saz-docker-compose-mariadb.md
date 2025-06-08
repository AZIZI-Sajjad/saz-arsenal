# saz-docker-compose-mariadb
```
#plateform/windows & linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/docker-compose-mariadb
```


## Docker compose mariadb - docker-compose.yml for mariadb + mariadb adminer tools (web base)
```
mkdir <Docker-compose.yml_file_location>
    ##-> mkdir /home/sda/docker/docker-compose.d/mariadb
cd <Docker-compose.yml_file_location>
nano docker-compose.yml
    ##-> Use root/<Mariadb_Root_Password> as user/password credentials
    version: '3.1'
    services:
    db:
        image: mariadb
        restart: always
        environment:
        MARIADB_ROOT_PASSWORD: <Mariadb_Root_Password>
    adminer:
        image: adminer
        restart: always
        ports:
        - <Linux_Local_port>:8080 # <Adminer_Default_HTTP_Port>
sudo docker compose -f <Docker-compose.yml_file_location> up -d
    ##-> Now open http://IP:<Linux_Local_port>
```