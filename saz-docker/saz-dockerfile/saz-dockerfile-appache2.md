# saz-dockerfile-appache2
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/dockerfile-appache2
```




## Docker apache2 - image HTTP basic
```
mkdir /home/sda/docker/Dockerfile.d/apache2
cd /home/sda/docker/Dockerfile.d/apache2
nano -c Dockerfile
    FROM httpd:2.4
    COPY <DIR_in_Linux_Local> <DIR_In_Container>
    ## DEFAULT -> COPY ./public-html/ /usr/local/apache2/htdocs/
    ## /!\ It must to create the folder "./public-html/" in current DIR ou give a existing folder
docker build -t Dockerfile .
OR
docker run -dit --network <Docker_Network_Name> --name <Container_Name> -p <Linux_Host_Listen_Port>:<Container_Listen_port> <Docker_Image_Name>
```




## Docker apache2 - image HTTPS basic
```
mkdir /home/sda/docker/Dockerfile.d/apache2
cd /home/sda/docker/Dockerfile.d/apache2
nano -c Dockerfile
    FROM httpd:2.4
    COPY <DIR_in_Linux_Local> <DIR_In_Container>
    ## DEFAULT -> COPY ./public-html/ /usr/local/apache2/htdocs/
    ## /!\ It must to create the folder "./public-html/" in current DIR ou give a existing folder

    ## Activate HTTPS SSL
    RUN sed -i \
        -e 's/^#\(Include .*httpd-ssl.conf\)/\1/' \
        -e 's/^#\(LoadModule .*mod_ssl.so\)/\1/' \
        -e 's/^#\(LoadModule .*mod_socache_shmcb.so\)/\1/' \
        conf/httpd.conf
docker build -t Dockerfile .
OR
docker run -dit --network <Docker_Network_Name> --name <Container_Name> -p <Linux_Host_Listen_Port>:<Container_Listen_port> <Docker_Image_Name>
```




## Docker apache2 - image HTTP basic + Linux Basic tools & net-tools 
```
mkdir /home/sda/docker/Dockerfile.d/apache2
cd /home/sda/docker/Dockerfile.d/apache2
nano -c Dockerfile
    FROM httpd:2.4
    COPY <DIR_in_Linux_Local> <DIR_In_Container>
    ## DEFAULT -> COPY ./public-html/ /usr/local/apache2/htdocs/
    ## /!\ It must to create the folder "./public-html/" in current DIR ou give a existing folder

    ## Install Linux Network basics tools & others
    ## coreutils : For install core tools like : cat ,
    ## RUN apt-get update && apt-get install -y coreutils && apt-get install -y net-tools && apt-get install -y vim && apt-get install -y nano && apt-get install -y curl && apt-get install -y iproute2 && apt-get install -y openssh-server && apt-get install -y openssh-client
    RUN apt-get update && apt-get install -y coreutils net-tools vim nano curl iproute2 openssh-server openssh-client
docker build -t Dockerfile .
OR
docker run -dit --network <Docker_Network_Name> --name <Container_Name> -p <Linux_Host_Listen_Port>:<Container_Listen_port> <Docker_Image_Name>
```




## Docker apache2 - image HTTPS basic + Linux Basic tools & net-tools 
```
mkdir /home/sda/docker/Dockerfile.d/apache2
cd /home/sda/docker/Dockerfile.d/apache2
nano -c Dockerfile
    FROM httpd:2.4
    COPY <DIR_in_Linux_Local> <DIR_In_Container>
    ## DEFAULT -> COPY ./public-html/ /usr/local/apache2/htdocs/
    ## /!\ It must to create the folder "./public-html/" in current DIR ou give a existing folder

    ## Install Linux Network basics tools & others
    ## coreutils : For install core tools like : cat ,
    ## RUN apt-get update && apt-get install -y coreutils && apt-get install -y net-tools && apt-get install -y vim && apt-get install -y nano && apt-get install -y curl && apt-get install -y iproute2 && apt-get install -y openssh-server && apt-get install -y openssh-client
    RUN apt-get update && apt-get install -y coreutils net-tools vim nano curl iproute2 openssh-server openssh-client

    ## Activate HTTPS SSL
    RUN sed -i \
        -e 's/^#\(Include .*httpd-ssl.conf\)/\1/' \
        -e 's/^#\(LoadModule .*mod_ssl.so\)/\1/' \
        -e 's/^#\(LoadModule .*mod_socache_shmcb.so\)/\1/' \
        conf/httpd.conf
docker build -t Dockerfile .
OR
docker run -dit --network <Docker_Network_Name> --name <Container_Name> -p <Linux_Host_Listen_Port>:<Container_Listen_port> <Docker_Image_Name>
```


