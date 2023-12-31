# saz-docker-apache2

#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/curl


# Docker apache2 - image basic
mkdir /home/sda/docker/Dockerfile.d/apache2
cd /home/sda/docker/Dockerfile.d/apache2
nano Dockerfile
    FROM httpd:2.4
    COPY <DIR_in_Linux_Local> <DIR_In_Container>
    ## DEFAULT -> COPY ./public-html/ /usr/local/apache2/htdocs/
    ## /!\ It must to create the folder "./public-html/" in current DIR ou give a existing folder
docker build -t <Docker_Image_Name> .
docker run -dit --network <Docker_Network_Name> --name <COntainer_Name> -p 8080:80 <Docker_Image_Name>


