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

## Linux - Add Route
```
sudo ip route add <Net_ID>/<Subnet_Prefix> via <GateWay_IP>
```
