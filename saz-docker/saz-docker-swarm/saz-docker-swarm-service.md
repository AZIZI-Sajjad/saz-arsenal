# saz-docker-swarm-service
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/docker-swarm-service
```

## Docker Swarm Service - Manual
```
Usage:  docker service COMMAND

Manage Swarm services

Commands:
  create      Create a new service
  inspect     Display detailed information on one or more services
  logs        Fetch the logs of a service or task
  ls          List services
  ps          List the tasks of one or more services
  rm          Remove one or more services
  rollback    Revert changes to a service's configuration
  scale       Scale one or multiple replicated services
  update      Update a service

Run 'docker service COMMAND --help' for more information on a command.

```


## Docker Swarm Service - Create a Service as service on all neouds in Swarm cluster 
```
docker service create \
  --publish \
    <host_port>:<Service_port> \
  --name <Service_Name> \
    <Image_name>:<Image_Version>
```


## Docker Swarm Service - Create a Service as service on all neouds in Swarm cluster + Nomber of Noeuds that run the service
```
docker service create \
  --publish \
  <host_port>:<Service_port> \
  --name <Service_Name> \
  --replicas <Nomber_Of_Replicas> <Image_name>:<Image_Version>
```


## Docker Swarm Service - Liste services (Containers) - Get Container {{ ID }} - {{ Name }} - {{ Mode }}- {{ Replicas }} - {{ Image }} - {{ Ports }} 
```
docker service ls
```


## Docker Swarm Service - inspect service (Container) - {{ ID }} - {{ NAME }}  - {{ IMAGE }}  - {{ NODE }}  - {{ DISIRED STATE }}  - {{ CURRENT STATE }}  - {{ ERROR }}  - {{ PORTS }}
```
docker service ps <Swarm_Service_Name>
```


## Docker Swarm Service - Scale a service (Change Nomber of Replicas -> Nodes run the serviec) 
```
  #### We can choose more than or less than
docker service scale <Service_Name>=<Number_Of_Neouds>
```


## Docker Swarm Service - Scale a service On Nodes - Mono Lable
```
docker service scale <Service_Name> \
  replicas <Number_Of_Neouds> \
  --constraint node.labels.region==<Label-1>
  --constraint node.labels.region==<Label-2>
```


## Docker Swarm Service - Scale a service On Nodes - Multi Lables
```
docker service scale <Service_Name> \
  replicas <Number_Of_Neouds> \
  --constraint node.labels.region==<Tag_Name>
```


## Docker Swarm Service - Scale a service On Nodes by Name
```
docker service scale \
  --mode=replicated \
  --replicas=<Actuel_Repicas+1> \
  --constraint 'node.hostname==<Worker_Name>' <Service_Name>
```


## Docker Swarm Service - Update a service "EXEMPLE ngnix"
```
  #### Add port to container
docker service update \
  --publish-add 80 my_web

  #### Remove port from container
docker service update \
  --publish-remove 80 my_web
```


## Docker Swarm Service - Inspect Service
```
docker service inspect <Service_Name> | more
```


## Docker Swarm Service - Remove Service
```
docker service rm <Service_Name>
```


## Docker Swarm Service - RollBack Service to privius configuation
```
docker service rollback <Service_Name>
```

## Docker Swarm Service - create a service with DIGEST 
```
  # Exemple:
docker service create \
  --name=<Service_Name> \
  ubuntu:16.04@sha256:35bc48a1ca97c3971611dc4662d08d131869daa692acb281c7e9e052924e38b1
```


## Docker Swarm Service - Mode Global - Service on All Veouds in Swarm Cluster
```
docker service create \
  --mode global \
  --publish mode=host,target=<host_port>,published=<Service_port> \
  --name=<Service_Name> \
  <<Image_name>:<Image_Version>>
```


## Docker Swarm Service - Mode Global - Run Service on Defined Network
```
docker service create \
  --replicas <Nombrer_Of_Replicas> \
  --publish mode=host,target=<host_port>,published=<Service_port> \
  --name=<Service_Name> \
  --network=<OverLay_Network_Name> \
  <<Image_name>:<Image_Version>>
```


## Docker Swarm Service - Create a Service as service on all neouds in Swarm cluster 
```
docker service create \
  --publish \
    <host_port>:<Service_port> \
  --name <Service_Name> \
    <Image_name>:<Image_Version>
```


## Docker Swarm Service - Connect a Service as service on all neouds in Swarm cluster 
```
docker service pdate \
  --network-add <OverLay_Network_Name> \
    <Service_Name>
```


## Docker Swarm Service - DisConnect a Service as service on all neouds in Swarm cluster 
```
docker service pdate \
  --network-rm <OverLay_Network_Name> \
    <Service_Name>
```
