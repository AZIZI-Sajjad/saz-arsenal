# saz-zimbra
```
#plateform/windows & Linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/zimbra
```

## zimbra - Get User's Inforamtion 
```
    # su zimbra
zmprov sa -v "mail=<Adress_Mail>" 
```


## zimbra - Get User's Information -  All Users in Domaine
```
    # su zimbra
zmprov sa -v "mail=*@<Domaine>" 
```

## zimbra - Get User's Information - Changed Pasword Time 
```
    # su zimbra
zmprov sa -v "mail=<Adress_Mail>" | egrep '^mail:|zimbraPasswordModifiedTime:|^$'
```


## zimbra - Get User's Information - Changed Pasword Time - All Usres in Domaine
```
    # su zimbra
zmprov sa -v "mail=<Domaine>" | egrep '^mail:|zimbraPasswordModifiedTime:|^$'
```

