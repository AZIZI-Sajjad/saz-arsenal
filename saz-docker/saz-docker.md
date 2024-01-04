# saz-docker
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/docker
```

## Docker restart service
```
systemctl restart docker
```


## Docker run an image and delete immediatly after launch to test the image
```
docker run -dit --rm <image_name>
```


## Docker rename an image 
```
    ### Step-1 : add new name & tag to image
docker tag <New_Image_Name>:<New_Image_Tag>

    ### Step-2 : remove old name & tag
docker rmi <Old_Image_Name>:<Old_Image_Tag>
```


## Docker run a container with specified {{ -dit }} {{ --rm }} {{name}} & {{port}} & {{network}} & {{data_persitence}} & {{image_Version}}
```
docker run -dit --rm -port<host_port>:<Container_port> --name <Container_Name> --network <network_Name> <Image_name>:<Image_Version>
```


## Docker run a container with specified {{ -dit }} {{ --rm }} {{name}} & {{port}} & {{network}} & {{data_persitence}} & {{image_Version}}
```
docker run -dit --rm -port<host_port>:<Container_port> --name <Container_Name> --network <network_Name> <Image_name>:<Image_Version>
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


## Docker - Create Network simple
```
sudo docker network crete <New_Docker_Network_Name>
```


## Docker - Create Network with {{ subnet }} {{ GateWay }} {{ DNS }}
```
docker network create \
    --driver=bridge \
    --subnet=<Network_ID/Subnet> \
    --ip-range=<Network_ID/Subnet> \
    --gateway=<GateWay_IP> \
    --opt "com.docker.network.bridge.name=dns" \
    --opt "com.docker.network.bridge.enable_ip_masquerade=false" \
    --opt "com.docker.network.bridge.enable_icc=false" \
    --opt "com.docker.network.bridge.host_binding_ipv4=0.0.0.0" \
    --opt "com.docker.network.driver.mtu=9001" \
    --opt "com.docker.network.bridge.dns=<GateWay_IP>" \
    <New_Docker_Network_Name>
```


## Docker - Disconnect container from Docker Network 
```
sudo docker network disconnect <Docker_Network_Name> <Container-Name_Or_ID>
```
