# saz-docker-mariadb
```
#plateform/windows & linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/docker-mariadb
```

## Docker mariadb - pull latest version
```
docker pull mariadb
```

## Docker mariadb - pull latest version by specify mariadb root password (1)
```
docker run -dit --name some-mariadb --env MARIADB_ROOT_PASSWORD=my-secret-pw --hostname <Container_HostName> mariadb:latest
```

## Docker mariadb - pull latest version No password for root (2)
```
docker run -dit --name some-mariadb --env MARIADB_ALLOW_EMPTY_ROOT_PASSWORD=1 --hostname <Container_HostName> mariadb:latest
```

## Docker mariadb - pull latest version - the container logs will contain the generated root password.
```
docker run -dit --name some-mariadb --env MARIADB_RANDOM_ROOT_PASSWORD=1 --hostname <Container_HostName> mariadb:latest
```
