# saz-docker-swarm-stack
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/docker-swarm-stack
```

## Docker Swarm Stack - Manual
```
Usage:  docker stack COMMAND

Manage Swarm stacks

Commands:
  config      Outputs the final config file, after doing merges and interpolations
  deploy      Deploy a new stack or update an existing stack
  ls          List stacks
  ps          List the tasks in the stack
  rm          Remove one or more stacks
  services    List the services in the stack

Run 'docker stack COMMAND --help' for more information on a command.
```


## Docker Swarm Stack - deploy a Stack by using Docker-Compose File
```
docker stack deploy --compose-file <Docker-Compose_File.yml>
```


## Docker Swarm Stack - Get All Stacks
```
docker stack ls
```


## Docker Swarm Stack - Get Stack's Containers
```
docker stack ps <Docker_Swarm_Stack_Name>
```


## Docker Swarm Stack - Get Stack's Micro-Services
```
docker stack service <Docker_Swarm_Stack_Name>
```


## Docker Swarm Stack - Remove Stack
```
docker stack rm <Docker_Swarm_Stack_Name>
```