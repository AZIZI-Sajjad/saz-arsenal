# saz-docker

#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/curl

## Docker restart service
systemctl restart docker

## Docker run an image and delete immediatly after launch to test the image
docker run --rm <image_name>

## Docker run a container with specified {{name}} & {{port}} & {{network}} & {{data_persitence}} & {{image_Version}}
docker run --rm -port<host_port>:<Container_port> --name <Container_Name> --network <network_Name> <Image_name>:<Image_Version>

## Docker run a container with specified {{ -it }} {{name}} & {{port}} & {{network}} & {{data_persitence}} & {{image_Version}}
docker run --rm -port<host_port>:<Container_port> --name <Container_Name> --network <network_Name> <Image_name>:<Image_Version>

## Docker busybox RUN Command by BusyBox
docker run busybox <Bash_Commande>

## Docker busybox run interactive
docker run --rm --name <Container_Name> --network <network_Name> <Image_name>:<Image_Version>

