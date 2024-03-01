# saz-linux-snmp

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/linux-snmp


## linux SNMP - Install UBUNTU & Debian
```
apt-get install snmpd
```


## linux SNMP - Configuration & securisation
```
    #### 1- SNMP Configuration
cp /etc/snmp/snmpd.conf /etc/snmp/snmpd.conf.bkp
nano -c /etc/snmp/snmpd.conf
createUser <snmp_community> MD5 <SNMP_v3_Password> DES
rouser <snmp_community> priv
    #### 2- SNMP securisation - Allow Only one IP to send SNMP TRAPs
sudo ufw allow from <IP_Source> to any port 161
```

