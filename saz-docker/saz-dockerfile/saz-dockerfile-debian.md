# saz-dockerFile-debian
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/saz-dockerFile-debian
```

## Dockerfile debian container + basics tools
```
mkdir /home/sda/docker/Dockerfile.d/debian
cd /home/sda/docker/Dockerfile.d/debian
nano -c <Dockerfile_Name>
    FROM debian
    RUN rm -rf /var/lib/apt/lists/*
    RUN apt-get update
    RUN apt-get install -y iputils-ping traceroute coreutils net-tools vim nano curl iproute2 openssh-server openssh-client sshpass
    ENV TZ="Europe/Paris"
    RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
    ENV LANG en_US.UTF-8
    CMD ["/bin/bash"]

sudo docker build -t <New_Image_Name>:<tag> -f <Dockerfile_Name> <Dockerfile_DIR>
sudo docker run -dit --network <Docker_Network_Name> --name <container_Name> <New_Image_Name>:<tag>
```


## Dockerfile debian container RUN with TTY
```
sudo docker exec -it <container_Name> /bin/bash
```
