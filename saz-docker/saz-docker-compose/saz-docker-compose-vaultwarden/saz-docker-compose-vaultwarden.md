# saz-docker-compose-vaultwarden

```
#plateform/windows & linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/docker-compose-vaultwarden
```


## docker-compose-vaultwarden - 1/2
```
    #### USE THESE VARIABLE IN DOCKER-COMPOSE
MYSQL_PASSWORD=$(pwgen --capitalize --numerals --symbols -1 32 1 -r o0O1IIlij\:\'\`\,\.\!\;\^\~\{\}\"\<\>\(\)\[\]\|\/\\)
ADMIN_TOKEN=$(echo -n $MYSQL_PASSWORD | sudo argon2 "$(openssl rand -base64 32)" -e -id -k 65540 -t 3 -p 4 | sed 's#\$#\$\$#g')
MARIADB_ROOT_PASSWORD_HASH=$MYSQL_PASSWORD
echo 'MARIADB_ROOT_PASSWORD_HASH:' $MARIADB_ROOT_PASSWORD_HASH
echo 'ADMIN_TOKEN:' $ADMIN_TOKEN
```


## docker-compose-vaultwarden - 2/2
```
    #### ONE NOTE
  ## Ref : https://github.com/dani-garcia/vaultwarden/wiki

version: "3.7"
services:
  mariadb:
    #image: "mariadb:latest"
    build:
      context: .
      dockerfile: Dockerfile-mariadb
    container_name: "mariadb"
    hostname: "mariadb"
    restart: always
    #  env_file:
    #   - ".env"
    volumes:
      - "mariadb_vol:/var/lib/mysql"
      - "/etc/localtime:/etc/localtime:ro"
      # Mount the SQL script
      # - "./init.sql:/docker-entrypoint-initdb.d/init.sql"
    environment:
      - "MARIADB_ROOT_PASSWORD_HASH=<MARIADB_ROOT_PASSWORD_HASH>"
      - "MYSQL_PASSWORD=<MYSQL_PASSWORD>"
      - "MYSQL_DATABASE=vaultwarden"
      - "MYSQL_USER=<MYSQL_USER>"

  vaultwarden:
    build:
      context: .
      dockerfile: Dockerfile-vaultwarden
    # image: "vaultwarden/server:latest"
    container_name: "vaultwarden"
    hostname: "vaultwarden"
    restart: always
    env_file:
      - ".env"
    volumes:
      - "vaultwarden_vol:/data/"
    environment:
      - "MARIADB_ROOT_PASSWORD_HASH=<MARIADB_ROOT_PASSWORD_HASH>"
      - "MYSQL_PASSWORD=<MYSQL_PASSWORD>"
      - "MYSQL_DATABASE=vaultwarden"
      - "MYSQL_USER=<MYSQL_USER>"
      ## Had issues when using single parentheses around the mysql URL as in the plain docker example
      - "DATABASE_URL=mysql://<MYSQL_USER>:<MYSQL_PASSWORD>@mariadb/<MYSQL_DATABASE>"
      # - "ADMIN_TOKEN=${VAULT_ADMIN_TOKEN}"
      - "ADMIN_TOKEN=<ADMIN_TOKEN>"
      - "RUST_BACKTRACE=1"
      - "SIGNUPS_ALLOWED=true"
      - "INVITATIONS_ALLOWED=true"
    ports:
      - "8080:80"
    depends_on:
      - mariadb
    networks:
      vaultwarden_network:
        ipv4_address: "172.32.0.100"
  # ldap_sync:
  #   image: vividboarder/vaultwarden_ldap
  #   volumes:
  #     - ./ldap.config.toml:/config.toml:ro
  #     # ./root.cert:/usr/src/vaultwarden_ldap/root.cert:ro
  #   environment:
  #     CONFIG_PATH: /config.toml
  #     RUST_BACKTRACE: 1
  #   depends_on:
  #     - vaultwarden
  #     - ldap
  #   restart: always

  # ldap:
  #   image: osixia/openldap
  #   volumes:
  #     - /var/lib/ldap
  #     - /etc/ldap/slapd.d
  #   environment:
  #     LDAP_READONLY_USER: 'true'
  #     LDAP_READONLY_USER_USERNAME: readonly
  #     LDAP_READONLY_USER_PASSWORD: readonly

  # ldap_admin:
  #   image: osixia/phpldapadmin
  #   ports:
  #     - 8001:80
  #   environment:
  #     PHPLDAPADMIN_HTTPS: 'false'
  #     PHPLDAPADMIN_LDAP_HOSTS: ldap
  #   depends_on:
  #     - ldap

volumes:
  vaultwarden_vol:
  mariadb_vol:


networks:
  vaultwarden_network:
    driver: bridge
    ipam:
      driver: default
      config:
        - subnet: "172.32.0.0/16"
          gateway: "172.32.0.1"

```
