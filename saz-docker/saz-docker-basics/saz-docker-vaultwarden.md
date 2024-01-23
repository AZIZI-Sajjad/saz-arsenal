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
sudo docker run -d --name vaultwarden -v /vw-data/:/data/ --network macnet3-0 --ip $IP --restart unless-stopped -e ADMIN_TOKEN=$ZMAR_TOKEN vaultwarden/server:latest
    #### In a Web Browser : 
lynx http://$IP/admin -> Paste the ADMIN_TOKEN
```

