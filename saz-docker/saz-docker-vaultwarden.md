# saz-docker-vaultwarden

#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/curl


# Docker busybox - custom image - instal a curl
mkdir /home/sda/docker/Dockerfile.d/busybox
cd /home/sda/docker/Dockerfile.d/busybox
nano Dockerfile
    FROM busybox

    ## Install curl inside the BusyBox image
    RUN wget -O /bin/curl https://curl.se/download/curl-7.82.0.tar.gz && \
            tar -xzf /bin/curl -C /bin/ && \
            chmod +x /bin/curl
            ## rm /bin/curl

    ## Set the working directory (optional)
    WORKDIR /app

    ## Your additional commands or configurations (optional)
    ## ...
    ## Command to run when the container starts
    CMD ["/bin/sh"]

sudo docker build -t custom-busybox-with-curl:v2 .
sudo docker run -dit --network net-busybox-apache2 --name container-busybox-curl custom-busybox-with-curl:v2





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
