# saz-exchange-powershell

#plateform/windows
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/exchange-powershell

## Exchange 2019 PowerShell - Change BAL DataBase
```
    #### All BAL in "Source_DataBase" in "Domaine" and move them to "Destination_DataBase"
Get-Mailbox -Database <Source_DataBase> -Filter {EmailAddresses -like '*.@<Domaine>'} | New-MoveRequest -TargetDatabase <Destination_DataBase>
```


## Exchange 2019 PowerShell - Export All BAL List in a DataBase
```
Get-Mailbox -Database <DataBaseName> | select WindowsEmailAddress | Export-Csv C:\tmp\Mailboxes<DataBaseName>.csv -NoTypeInformation -Encoding UTF8
```



## Exchange 2019 PowerShell - Export All BAL list by Domaine and save in CSV
```
Get-Mailbox -ResultSize unlimited | where {$_.emailAddresses -like "*@<DomaineName>" } | Export-Csv C:\tmp\<DomaineName>-all-mails.csv -NoTypeInformation -Encoding UTF8
```


## Exchange 2019 PowerShell - Export All BAL list by Domaine
```
Get-Mailbox -ResultSize unlimited | where {$_.emailAddresses -like "*@<DomaineName>" }
```



## Exchange 2019 PowerShell - Get All DataBases
```
Get-MailboxDatabase | select Name,DatabaseSize,server,AvailableNewMailboxSpace
```


## Exchange 2019 PowerShell - Get All DataBases and Filter by Server
```
Get-MailboxDatabase | select Name,DatabaseSize,server,AvailableNewMailboxSpace | where {$_.server -like '<DataBase>*'}
```


## Exchange 2019 PowerShell - Mailbox Export Request Statistics by Adresse Mail
```
Get-MailboxExportRequestStatistics -Identity <AdressMail>
```


## Exchange 2019 PowerShell - Give Access total on a Adressse Mail to Another Adresse Mail
```
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@adpam.asso.fr" } | Select-Object PrimarySmtpAddress, DisplayName, servername, Database | Format-Table
```


## Exchange 2019 PowerShell - Give Access total on a Adressse Mail to All Adresses Mails in domaine
```
Récupérer les d'un compte à toutes les boîtes aux lettres d'un domaine:
$delegateaccount='<Delegate_Adress>'; Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@<DomaineName>" } | get-MailboxPermission -User $delegateaccount
```


## Exchange 2019 PowerShell - 
```
ADPAM : Délégation BAL Migration@adpam.asso.fr à toutes les BAL :
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@adpam.asso.fr" }
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@adpam.asso.fr" } | Select-Object PrimarySmtpAddress, DisplayName, servername, Database | Format-Table
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@adpam.asso.fr" } | Add-MailboxPermission -AccessRights FullAccess -User migration@adpam.asso.fr
```


## Exchange 2019 PowerShell - 
```
Get les adresses Mail + Les Alias + Les Forward
Get-Mailbox -ResultSize unlimited | Where-Object { $_.EmailAddresses -like "*@albertdemun.fr" } | Select-Object DisplayName, ForwardingAddress, @{Name="PrimaryEmailAddress";Expression={$_.PrimarySmtpAddress}}, @{Name="Aliases";Expression={$_.EmailAddresses -replace '^.*?([^@]+)@albertdemun\.fr$', '$1'}} | Export-Csv -Path C:\tmp\albertdemun.fr.csv -NoTypeInformation -Encoding UTF8
```


## Exchange 2019 PowerShell - 
```

```


## Exchange 2019 PowerShell - 
```

```


## Exchange 2019 PowerShell - 
```

```


## Exchange 2019 PowerShell - 
```

```


## Exchange 2019 PowerShell - 
```

```


## Exchange 2019 PowerShell - 
```

```


## Exchange 2019 PowerShell - 
```

```


## Exchange 2019 PowerShell - 
```

```


## Exchange 2019 PowerShell - 
```

```


## Exchange 2019 PowerShell - 
```

```

