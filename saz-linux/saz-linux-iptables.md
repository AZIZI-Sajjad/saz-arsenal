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

## Linux-iptables - 
```

```

