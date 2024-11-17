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

## linux - nc Check TCP (t) port - 1
```
nc -zvw<time_out> <IP> <Port>
```

## linux - nc Check TCP (t) port - 2
```
nc -zvtw<time_out> <IP> <Port>
```


## linux - nc Check UDP (u) port
```
nc -zvuw<time_out> <IP> <Port>
```


## linux - restart multi services
```
systemctl restart php7.4-fpm apache2
```


## linux - Get IP Publique 1
```
wget -qO- http://ifconfig.me ; echo
```


## linux - Get IP Publique 2
```
curl -k https://ifconfie.me
```


## linux - Get IP Publique 3
```
curl -k https://monip.org
```


## linux - cat gz files - zcat
```
zcat *.gz
```


## linux - zgrep gz files - zcat
```
zgrep "pattern" *.gz
```


## linux - start service
```
systemctl start <service_Name>
```


## linux - stop service - systemctl
```
systemctl start <service_Name>
```


## linux - restart service - systemctl
```
systemctl restart <service_Name>
```


## linux - Enable service - systemctl
```
systemctl enable <service_Name>
```


## linux - Network Debian -  Second IP on Second NIC
```
    #### Add the following lines to "/etc/network/interfaces"
    #### nano -c /etc/network/interfaces
auto <NIC_Name>
iface NIC_Name> inet static
    address <IP_Adresse>
    netmask <SubnetMAsk>

```


## linux - share sftp ( sshfs )
```
sshfs -o allow_other,default_permissions -p <portNumber> <sftpUser>@<IP>:<sharePathOnRemoteServer> <LocalPathToMounttheShare>
```

