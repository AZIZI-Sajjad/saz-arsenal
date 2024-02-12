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


## Docker Swarm Cluster - Joint a Worker to Cluster
```
  ## Get join commande at cluster creation ## -> docker swarm init
docker swarm jopint --token <TOKEN>
```


## Docker Swarm Cluster - Swarm et Members (Managers & Workers)
```
docker node ls
```


## Docker Swarm Cluster - Inspect Cluster's nodes
```
docker node inspect <Membre_Name>
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
docker node node update --label-add <Label_key>=<Label_value> <Worker_Node_Name>

    #### Exemple : 
    # docker node node update --label-add dd=ssd worker00
    # docker node inspect --fromat "{{ .Spec.Labels }}" worker00

```

