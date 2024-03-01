# saz-docker-compose-exemple
```
#plateform/windows & linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/docker-compose-exemple
```


## docker-compose-exemple
```
    # Réf: https://wiki-tech.io/Conteneurisation/Docker/Docker-Compose
    # Réf : les fichiers de source du site utilisé dans cet article sur le site wiki-tech.io:
    # -> https://devopssec.fr/documents/docker/docker-compose/sources.zip
    # wget https://devopssec.fr/documents/docker/docker-compose/sources.zip



    ## 1/3 - nano Dockerfile
        FROM php:7-apache
        LABEL version="1.0" maintainer="AJDAINI Hatim &tl;ajdaini.hatim@gmail.com>"
        # Activation des modules php
        RUN docker-php-ext-install pdo pdo_mysql
        WORKDIR  /var/www/html
    ## Docker build -t myapp .




    ## 1/2 - nano docker-compose
        version: '3.7'

        # Mot clé pour dire qu'il y a plusieurs services "Conteneurs"
        services:

        # Créer un service "Conteneur" avec la configuration suivante
            db:

                # Se baser sur l’image
                image: mysql:5.7

                # Nommer le conteneur 
                container_name: mysql_c

                # Le conteneur démarrera automatiquement le conteneur en cas de redémarrage du serveur
                restart: always

                # Définir les volumes à créer et utiliser
                # (un volume pour exécuter automatiquement notre fichier sql et un autre pour sauvegarder les données de la base de données)
                volumes:
                    - db-volume:/var/lib/mysql
                    - ./articles.sql:/docker-entrypoint-initdb.d/articles.sql
                    
                # Surcharger les variables d’environnements à utiliser
                environment:
                    MYSQL_ROOT_PASSWORD: test
                    MYSQL_DATABASE: test
                    MYSQL_USER: test
                    MYSQL_PASSWORD: test

            app:
                image: myapp
                container_name: myapp_c
                restart: always
                volumes:
                    - ./app:/var/www/html
                ports:
                    - 8080:80
                depends_on:
                    - db

        volumes:
            db-volume:

    ## 3/3 - Créer le service avec docker-compose
    ## docker-compose up -d
    ## docker ps
    ## docker-compose ps







    ## Lancer les conteneurs sans le docker-compose
        docker run -d -e MYSQL_ROOT_PASSWORD='test' \
        -e MYSQL_DATABASE='test' \
        -e MYSQL_USER='test' \
        -e MYSQL_PASSWORD='test' \
        --volume db-volume:/var/lib/mysql \
        --volume $PWD/articles.sql:/docker-entrypoint-initdb.d/articles.sql \
        --name mysql_c mysql:5.7
    ## Lancer les conteneurs
    docker run -d --volume $PWD/app:/var/www/html -p 8080:80 --link mysql_c --name myapp_c myapp
```