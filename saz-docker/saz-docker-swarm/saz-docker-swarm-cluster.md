# ssaz-docker-swarm
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/docker-swarm
```

## Docker Swarm Cluster - Initiate Swarm Cluster 
```
docker swarm init
```


## Docker Swarm Cluster - Get join Token to join a WORKER on Manager
```
docker swarm join-token worker
```


## Docker Swarm Cluster - Get join Token to join a MANAGER on existing Manager
```
docker swarm join-token manager
```


## Docker Swarm Cluster - Joint a Worker to Cluster
```
  ## Get join commande at cluster creation ## -> docker swarm init
docker swarm jopint --token <TOKEN>
```


## Docker Swarm Cluster - Swarm et Members (Managers & Workers)
```
docker node ls
```


## Docker Swarm Cluster - Swarm et Members (Managers & Workers)
```
    #### Drain : No service on the Node and Shut Down existing Service(s) on This node
docker node update --availability drain <Node-Name>
```


## Docker Swarm Cluster - destroy cluster
```
    #### Leave on all Neouds (Workers & Managers) if necessary use --froce
docker swarm leave --force 
```


## Docker Swarm Cluster - Inspect Cluster's nodes
```
docker node inspect <Membre_Name>
```


## Docker Swarm Cluster - Inspect Cluster's nodes
```
docker node inspect <Membre_Name> --pretty
```


## Docker Swarm Cluster - Promote Manager Rule to orkers
```
docker node promote <Worker1-Name> <Worker2-Name> ... <WorkerN-Name>
```


## Docker Swarm Cluster - Demote Manager Role from Manager
```
docker node demote <MAnager1-Name> <MAnager2-Name> ... <MAnagerN-Name>
```


## Docker Swarm Cluster - Get specific information from inspect
```
  #### Exempe:
docker node ispect <Node_Name> --format "{{ .Status.Addr}}"
docker node ispect <Node_Name> --format "{{ .Status.State}}"
```


## Docker Swarm Cluster - List swarm services (containers) statues
```
docker node ps
```


## Docker Swarm Cluster - Remove Manager Role of Worker
```
docker node demote <Worker_Node_Name>
```


## Docker Swarm Cluster - Remoev a Worer from Swarm Cluster 
```
    #### 1- Connect to worker via SSH
    #### 2- Stop swarm service :
docker swarm leave
    #### 3- Remoe the Worke from Node List
```


## Docker Swarm Cluster - Update Node's Informations
```
--availability string           # Active / Pause / Darin 
                                # Active: 
                                # Pause : 
                                # Darin : Ne pas utiliser le Manager en tant que Worker, il porte de conteneurs 

--label-add -list               # Ajouter des tags, ou des Label au node -> à définir en format key=value
--label-rm list                 # supprimer des tag ou des label du node
--role string                   # worker / manager -> Changer le rôle du node

```


## Docker Swarm Cluster - Add Label "TAG" to a Cluster node:
```
docker node node update --label-add <Labe1l_key>=<Label1_value> --label-add <Label2_key>=<Label2_value> <Worker_Node_Name>

    #### Exemple : 
    # docker node node update --label-add dd=ssd --label-add bar=baz worker00
    # docker node inspect --fromat "{{ .Spec.Labels }}" worker00

```

