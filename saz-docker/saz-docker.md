# saz-docker

#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/docker

## Docker restart service
```
systemctl restart docker
```

## Docker run an image and delete immediatly after launch to test the image
```
docker run --rm <image_name>
```

## Docker run a container with specified {{name}} & {{port}} & {{network}} & {{data_persitence}} & {{image_Version}}
```
docker run --rm -port<host_port>:<Container_port> --name <Container_Name> --network <network_Name> <Image_name>:<Image_Version>
```

## Docker run a container with specified {{ -it }} {{name}} & {{port}} & {{network}} & {{data_persitence}} & {{image_Version}}
```
docker run --rm -port<host_port>:<Container_port> --name <Container_Name> --network <network_Name> <Image_name>:<Image_Version>
```

## Docker restart service
```
systemctl restart docker
```

## Docker - connect to a container  interactively
```
docker exec -it  <Container_Name> <bash_or_sh_mysql_etc>
```

## Docker - copy into a container
```
docker cp <source_files_or_folder> <container_name>:<container_destination_DIR>
```

## Docker - copy from a container
```
docker cp <container_name>:<container_destination_DIR> <source_files_or_folder>
```
