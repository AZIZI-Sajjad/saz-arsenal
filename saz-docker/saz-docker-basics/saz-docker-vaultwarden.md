# saz-docker-vaultwarden
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/docker-vaultwarden
```


## Vaultwarden - basic
```
sudo docker run -dit --name zmar -v /vw-data/:/data/ -p 8080:80 vaultwarden/server:latest
```


## Vaultwarden - Install Container Container conttected to the Physical Network IP in LAN Range
```
IP="<Container_IP>"
MySecretPassword="<MySecretPassword>"
    #### MySecretPassword -> Used to generate ADMIN_TOKEN
    #### macnet3-0 -> Is a DockerNork type "macvlan"
ZMAR_TOKEN=$(echo -n $MySecretPassword | sudo argon2 "$(openssl rand -base64 32)" -e -id -k 65540 -t 3 -p 4 | sed 's#\$#\$\$#g')
echo $ZMAR_TOKEN
sudo docker run -d --name vaultwarden -v /vw-data/:/data/ --network macnet3-0 --ip $IP --restart unless-stopped -e ADMIN_TOKEN=$ZMAR_TOKEN -- hostname <Container_HostName> vaultwarden/server:latest
    #### In a Web Browser : 
lynx http://$IP/admin -> Paste the ADMIN_TOKEN
```


## Vaultwarden - Install Container Container conttected to the Physical + SSL LetsEncrypt ????????????????????????????????

```
    #### Ref: https://github.com/dani-garcia/vaultwarden/wiki/Enabling-HTTPS
    #### /etc/letsencrypt/archive/mydomain
IP="<Container_IP>"
MySecretPassword=$(pwgen --capitalize --numerals --symbols -1 1 1 -r o0O1IIlij\:\'\`\,\.\!\;\^\~\{\}\"\<\>\(\)\[\]\|\/\\)
    #### MySecretPassword -> Used to generate ADMIN_TOKEN
    #### macnet3-0 -> Is a DockerNork type "macvlan"
ZMAR_TOKEN=$(echo -n $MySecretPassword | sudo argon2 "$(openssl rand -base64 32)" -e -id -k 65540 -t 3 -p 4 | sed 's#\$#\$\$#g')
echo $ZMAR_TOKEN

sudo docker run -d --name vaultwarden \
    -e ROCKET_TLS='{certs="/ssl/live/mydomain/fullchain.pem",key="/ssl/live/mydomain/privkey.pem"}' \
    -v /etc/letsencrypt/:/ssl/ \
    -v /var/zmar/data/:/data/ \
    -p 443:80 \
    --network macnet3-0 \
    --ip $IP \
    --restart unless-stopped \
    -e ADMIN_TOKEN=$ZMAR_TOKEN \
    --hostname <Container_HostName> \
    vaultwarden/server:latest \

    #### In a Web Browser : 
lynx http://$IP/admin -> Paste the ADMIN_TOKEN
```

