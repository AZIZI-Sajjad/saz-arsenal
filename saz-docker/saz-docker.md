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


## Docker run container  and delete image immediatly after launch to test the image
```
docker run -dit --rm <image_name>
```


## Docker rename an image 
```
    ### Step-1 : add new name & tag to image
docker tag <Old_Image_Name>:<Old_Image_Tag> <New_Image_Name>:<New_Image_Tag>

    ### Step-2 : remove old name & tag
docker rmi <Old_Image_Name>:<Old_Image_Tag>
```


## Docker connect to a container
```
docker attach <Container_Name>
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
    ### 1- Create New Interface On th Docker Host to pass docker Network - This is the Container's GATEWAY 
    sudo ip link add name <New_Docker_network_Name> type bridge
    sudo ip addr add <Gateway_IP> dev <New_Docker_network_Name>
    sudo ip link set dev <New_Docker_network_Name> up

    ### 2- Crete Docker Network type Overlay
    sudo docker network create \
        --subnet=<Network_ID/Subnet> \
        --ip-range=<Network_ID/Subnet> \
        --gateway=<Gateway_IP> \
        --attachable \
        --driver=overlay \
        --opt "com.docker.network.bridge.name"="<New_Docker_network_Name>" \
        --opt "com.docker.network.bridge.default_bridge"="true" \
        --opt "com.docker.network.bridge.enable_icc"="false" \
        --opt "com.docker.network.bridge.enable_ip_masquerade"="false" \
        --opt "com.docker.network.bridge.host_binding_ipv4"="0.0.0.0" \
        --opt "com.docker.network.driver.mtu"="1500" \
        <New_Docker_network_Name>
    
    ### Run the container and set its parameters
    sudo docker run -dit --name <Container_Name> --network <New_Docker_network_Name> --ip <Container_IP> --dns <Container_DNS> <Image_Name>:<Image_Tag>

### NOTE : Internet OK / Can not PING the docker network's NETWORK  / PING All other networks subnets OK 
```





















## Docker - Disconnect container from Docker Network 
```
sudo docker network disconnect <Docker_Network_Name> <Container-Name_Or_ID>
```





## Docker Errors - Error response from daemon: This node is not a swarm manager.
```
docker swarm init
```

