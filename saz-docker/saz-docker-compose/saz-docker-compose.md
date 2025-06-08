# saz-docker-compose

```
#plateform/windows & linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/docker-compose
```


## Docker-Compose - Get Version
```
docker compose --version
```


## Docker-Compose - List Containers & Networks Retlated to the Docker-Compose
```
docker compose ps
```


## Docker-Compose - Check docker-compose file's Configurations & Syntax
```
docker compose config
```


## Docker-Compose - Build a service
```
docker compose up (-d) (--build)
```


## Docker-Compose - Stop a service
```
docker compose stop
```


## Docker-Compose - Remove a service Only Containers
```
docker compose rm
```


## Docker-Compose - Remove a service & related Doker Network
```
docker compose down
```


## Docker-Compose - Remove a service & related Doker Network & VOLUMES
```
docker compose down
```


## Docker-Compose - Kill a service
```
docker compose kill
```


## Docker-Compose - Show Images built bu docker compose
```
docker compose images
```


## Docker-Compose - Remove Image built by docker compose
```
docker compose rm
```


## Docker-Compose - Show Docker compose LOGS
```
docker compose logs
```


## Docker-Compose - Show Docker compose LOGS continuously 1/2
```
docker compose --file <Docker-compose-File.yml> --project-name <project-Name> logs -f
```


## Docker-Compose - Show Docker compose LOGS continuously 2/2
```
docker compose --project-name <project-Name -> Get-By: docker compose ls> logs -f
```


## Docker-Compose - Create project
```
docker compose --file '/home/<Projet_Name>.fr/docker/docker-compose.yml' --project-name '<Projet_Name>' up
```


## Docker-Compose - Create project and show Logs
```
docker compose --file '/home/<Projet_Name>.fr/docker/docker-compose.yml' --project-name '<Projet_Name>' up -d
```


## Docker-Compose - with docker-compose Project
```
docker compose --file '/home/<Projet_Name>.fr/docker/docker-compose.yml' --project-name '<Projet_Name>' restart
```

## Docker-Compose - Define volume's local location in Docker compose file
```
volumes:
  vaultwarden_vol:
    driver: local
    driver_opts:
      type: none
      o: bind
      device: <chemin_absolu_sur_votre_machine_local>
  mariadb_vol:
    driver: local
    driver_opts:
      type: none
      o: bind
      device: <autre_chemin_absolu_sur_votre_machine_local>
```

