# saz-dockerfile-busybox

#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/dockerfile-busybox


## Docker busybox - custom image - instal a curl
```
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
```
