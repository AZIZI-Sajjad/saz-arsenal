# saz-linux

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/linux

## Linux - Get disks 
```
df -h
```

## Linux - Get folder and subfiles and folders 's size
```
du -h
```

## Linux - Get current folder's size
```
du -hs
```


## Linux - Grep - remove Emprty lines & comment - Exemple : a enabled site in apache :
```
cat /etc/apache2/sites-enabled/000-default.conf | grep -Ev "#|^$"
```

## Linux - Grep - remove Emprty lines & comment - Exemple : in php7.4-fpm Config :
```
cat /etc/php/7.4/fpm/php.ini | grep -Ev "#|^$|;"
```

## Linux - Add Route
```
sudo ip route add <Net_ID>/<Subnet_Prefix> via <GateWay_IP>
```


## Linux - letsencrypt - Generate certificat - validation with apache methode 
```
letsencrypt --apache -d <Domaine> --agree-tos
```


## Linux - base64 Encoding 
```
echo <string> | base64
```


## Linux - change user Shell to BASH 
```
chsh -s /bin/bash <User_Name>
```


## Linux - Generate Password without 
```
pwgen --capitalize --numerals --symbols -1 <Number_Of_Caracters> <Number_Of_password_To_Generate> -r o0O1IIl6b9q9ggqij\:\'\`\,\.\!\;\^\~\{\}\"\<\>\(\)\[\]\|\/\\
```

