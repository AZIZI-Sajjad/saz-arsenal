# saz-linux-rsync

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/linux-rsync

## Linux rsync - Copy from Remote Host SSH
```
sudo rsync -ah '<Remote_SSH_User>@<Remote_Server_SSH_IP>:<Source_Files_Folders_Remote_Server>' <Local_Files_Folders_Destination>
```

## Linux rsync - Copy to Remote Host SSH
```
sudo rsync -ah <Source_Files_Folders_Remote_Server> '<Remote_SSH_User>@<Remote_Server_SSH_IP>:<Local_Files_Folders_Destination>'
```

## Linux rsync - Copy to Remote Host SSH with Progress Bare & Prralels Tasks
```
rsync -ah --progress --parallel=4 <Source_Files_Folders_Remote_Server> '<Remote_SSH_User>@<Remote_Server_SSH_IP>:<Local_Files_Folders_Destination>'
