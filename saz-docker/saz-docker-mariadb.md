# saz-docker-mariadb

#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/curl


# Docker mariadb - pull latest version
docker pull mariadb

# Docker mariadb - pull latest version by specify mariadb root password (1)
docker run --detach --name some-mariadb --env MARIADB_ROOT_PASSWORD=my-secret-pw  mariadb:latest

# Docker mariadb - pull latest version No password for root (2)
docker run --detach --name some-mariadb --env MARIADB_ALLOW_EMPTY_ROOT_PASSWORD=1  mariadb:latest

# Docker mariadb - pull latest version - the container logs will contain the generated root password.
docker run --detach --name some-mariadb --env MARIADB_RANDOM_ROOT_PASSWORD=1  mariadb:latest


# Docker compose mariadb - docker-compose.yml for mariadb + mariadb adminer tools (web base)
mkdir <Docker-compose.yml_file_location>
    ##-> mkdir /home/sda/docker/docker-compose.d/mariadb
cd <Docker-compose.yml_file_location>
nano docker-compose-
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
