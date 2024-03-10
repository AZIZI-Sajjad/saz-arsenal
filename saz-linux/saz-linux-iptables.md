# saz-linux-iptables

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/linux-iptables

## Linux-iptables - Permanents Rules
```
    #### Réf: https://www.cyberciti.biz/faq/how-to-save-iptables-firewall-rules-permanently-on-linux/

    #### 1 : Install iptables-persistent
    sudo apt-get install iptables-persistent
    #### 2 : Activate service & Start it
    sudo systemctl is-enabled netfilter-persistent.service
    sudo systemctl enable netfilter-persistent.service
    sudo systemctl status netfilter-persistent.service

    #### 3 : Debian or Ubuntu :
    sudo /sbin/iptables-restore < /etc/iptables/rules.v4
    sudo /sbin/ip6tables-restore < /etc/iptables/rules.v6
    
    #### 3 : CentOS/RHEL:
    sudo /sbin/iptables-restore < /etc/sysconfig/iptables
    sudo /sbin/ip6tables-restore < /etc/sysconfig/ip6tables

```


## DATA CENTER - iptables Install Permanent - UBUNTU 
```
apt install iptables-persistent
apt-get install iptables-persistent
systemctl is-enabled netfilter-persistent.service
systemctl enable netfilter-persistent.service
systemctl status netfilter-persistent.service
```


## DATA CENTER - iptables Install Permanent - CentOS
```
yum install iptables-services
systemctl enable iptables
systemctl enable ip6tables
systemctl status iptables
```


## DATA CENTER - iptables Permanent - Backup
```
iptables-save -c > /etc/iptables/rules.v4
```


## DATA CENTER - iptables Permanent - Restore
```
iptables-restore < /etc/iptables/rules.v4
```


## DATA CENTER - iptables Permanent - Backup & Restore
```
iptables-save -c > /etc/iptables/rules.v4
iptables-restore < /etc/iptables/rules.v4
```