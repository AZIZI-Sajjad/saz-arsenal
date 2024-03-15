# saz-VsCode

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/VsCode

## VsCode - Connexion SSH
```
Host <Connection_Name>
  Hostname <Remote_SSH_Server_IP>
  User <Remote_SSH_Server_USER>
```

## VsCode - Connexion SSH + Sudo 
```
Host <Connection_Name>
  Hostname <Remote_SSH_Server_IP>
  User <Remote_SSH_Server_USER>
  RemoteCommand sudo -i
```