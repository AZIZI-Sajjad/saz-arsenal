# saz-docker-machine
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/docker-machine
```

## Docker machine -  cretae a docker-machine
```
docker-machine create –driver <Driver-virtualbox-myhyperv-vmware-etc> <Docker_Machine_Name>

```

## Docker machine -  cretae a docker-machine On Remote Host
```
    #### you’ll see the remote docker vm host that we created. On your local system
docker-machine create -d <Driver-virtualbox-myhyperv-vmware-etc> \
  --generic-ip-address <Remote_Host_IP> \ 
  --generic-ssh-key <$HOME/.ssh/id_rsa> \
  --generic-ssh-user <Remote_user_name> \
  --generic-ssh-port <SSH_Port> \
  <Docker-Machine_Name>
```


## Docker machine - List docker-machines
```
docker-machine ls
```


## Docker machine - start a docker-machine
```
docker-machine start <Docker_Machine_Name>
```


## Docker machine -  restart a docker-machine
```
docker-machine restart <Docker_Machine_name>
```


## Docker machine -  remove a docker-machine
```
docker-machine rm <Docker_Machine_name>
```

## Docker machine -  Connect to docker-machine PowerShell
```
    #### 1- Get Connection information of Docker Machine
docker-machine ls
docker-machine env <Docker_Machine_name>
    #### 2- Connection PowerShell
docker-machine env <Docker_Machine_name>
docker-machine env <Docker_Machine_name> | Invoke-Expression
```

## Docker machine -  Connect to docker-machine SSH
```
docker-machine ssh <Docker_Machine_name>
```
