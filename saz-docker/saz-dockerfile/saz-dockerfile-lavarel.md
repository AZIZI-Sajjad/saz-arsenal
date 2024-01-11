# saz-dockerfile-lavarel

```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/dockerfile-lavarel
```

## Dockerfile - lavarel PHP8.1
```
    ####
    #### Réf: https://www.it-connect.fr/installation-de-php-8-1-sur-debian-11-pour-son-serveur-web/

    FROM debian:bullseye

    #### Mise à jour des listes de paquets et installation des paquets nécessaires
    RUN apt-get update \
        && apt-get install -y --no-install-recommends \
            coreutils iputils-ping traceroute netcat-openbsd dnsutils net-tools vim nano curl iproute2 openssh-server openssh-client sshpass python3 python3-pip certbot python3-certbot-apache \
            ca-certificates apt-transport-https software-properties-common wget lsb-release

    #### Ajout du dépôt PHP 8.1
    RUN curl -sSL https://packages.sury.org/php/README.txt | bash -x
    RUN apt-get update

    #### Installation de PHP 8.1
    RUN apt-get install -y --no-install-recommends php8.1

    #### Pour permettre l'intégration de PHP avec Apache
    RUN apt-get install -y --no-install-recommends libapache2-mod-php8.1

    #### Redémarrage d'Apache
    #### RUN systemctl restart apache2

    #### Afficher la version de PHP
    RUN php -v

    #### Installation de PHP8.1-FPM et PHP8.1-cli
    RUN apt-get install -y --no-install-recommends php8.1-fpm php8.1-cli

    #### Installation des extensions PHP
    RUN apt-get install -y --no-install-recommends php8.1-common php8.1-curl php8.1-bcmath php8.1-intl php8.1-mbstring php8.1-xmlrpc php8.1-mcrypt php8.1-mysql php8.1-gd php8.1-xml php8.1-cli php8.1-zip

    #### Module PHP-FM pour les performances d'Apache
    RUN apt-get install -y --no-install-recommends php8.1-fpm libapache2-mod-fcgid

    #### Activation des modules de performances d'Apache pour FPM
    RUN a2enmod proxy_fcgi setenvif
    RUN a2enconf php8.1-fpm

    #### Redémarrage de PHP8.1-FPM
    #### RUN systemctl restart php8.1-fpm
    RUN service php8.1-fpm restart

    ENV LANG en_US.UTF-8
    CMD ["/bin/bash"]

```




## Dockerfile - lavarel MYSQL 5.7
```
    #### 
    #### Réf: https://www.it-connect.fr/installation-de-php-8-1-sur-debian-11-pour-son-serveur-web/

    FROM debian:bullseye

    #### Mise à jour des listes de paquets et installation des paquets nécessaires
    RUN apt-get update \
        && apt-get install -y --no-install-recommends \
            coreutils iputils-ping traceroute netcat-openbsd dnsutils net-tools vim nano curl iproute2 openssh-server openssh-client sshpass python3 python3-pip certbot python3-certbot-apache \
            ca-certificates apt-transport-https software-properties-common wget lsb-release


    RUN mkdir ~/tmp
    WORKDIR ~/tmp

    RUN wget https://dev.mysql.com/get/mysql-apt-config_0.8.22-1_all.deb
    RUN echo -e "Ok \n" | apt-get install -y ./mysql-apt-config_0.8.22-1_all.deb -
    RUN apt update
    RUN apt install -y mysql-server
    RUN service mysql status
```



