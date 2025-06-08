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


## Exchange 2019 PowerShell - Get Mailbox Export Request's Statistics
```
Get-MailboxExportRequest | Get-MailboxExportRequestStatistics
```


## Exchange 2019 PowerShell - Give Access total on a Adressse Mail to Another Adresse Mail
```
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@<MailDomaine>" } | Select-Object PrimarySmtpAddress, DisplayName, servername, Database | Format-Table
```


## Exchange 2019 PowerShell - Give Access total on a Adressse Mail to All Adresses Mails in domaine
```
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@<MailDomaine>" } | Add-MailboxPermission -AccessRights FullAccess -User <DelegateAccount>


    # Check:
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@<DomaineName>" } | get-MailboxPermission -User <DelegateAccount>
```


## Exchange 2019 PowerShell - Delegate access to All Adresses mails in Domaine To an Address Mail
```
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@<MailDomaine>" }
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@<MailDomaine>" } | Select-Object PrimarySmtpAddress, DisplayName, servername, Database | Format-Table
Get-Mailbox -ResultSize Unlimited | where {$_.emailAddresses -like "*@<MailDomaine>" } | Add-MailboxPermission -AccessRights FullAccess -User <DelegateAccount>
```


## Exchange 2019 PowerShell - Get les adresses Mail + Les Alias + Les Forward
```
Get-Mailbox -ResultSize unlimited | Where-Object { $_.EmailAddresses -like "*@albertdemun.fr" } | Select-Object DisplayName, ForwardingAddress, @{Name="PrimaryEmailAddress";Expression={$_.PrimarySmtpAddress}}, @{Name="Aliases";Expression={$_.EmailAddresses -replace '^.*?([^@]+)@albertdemun\.fr$', '$1'}} | Export-Csv -Path C:\tmp\albertdemun.fr.csv -NoTypeInformation -Encoding UTF8
```


## Exchange 2019 PowerShell - Get MoveRequest
```
Get-MoveRequest
```


## Exchange 2019 PowerShell - Get MoveRequest In Porcentage
```
Get-MoveRequest | ForEach-Object { $stats = Get-MoveRequestStatistics -Identity $_.Identity; "$($stats.TargetMailbox) - Percentage Completion: $($stats.PercentComplete)%" }
```


## Exchange 2019 PowerShell - Get All MailBoxes size + Adresses + ALias and save as csv File
```
Get-Mailbox -ResultSize unlimited | sort-object | Select-Object name,alias,servername,ProhibitSendQuota,IssueWarningQuota,MaxReceiveSize,MaxSendSize,DisplayName,Database,PrimarySmtpAddress,ProhibitSendReceiveQuota,@{n="Size(MB)";e = {$MBXstat = Get-MailboxStatistics $_.name; $MBXstat.totalItemsize.value.ToMB()}},@{n="Items"; e = {$MBXstat = Get-MailboxStatistics $_.name ; $MBXstat.itemcount; $MBXstat.storageLimitStatus}},@{n="LastLogon"; e=  {$MBXstat = Get-MailboxStatistics $_.name ; $MBXstat.LastLogonTime}} | Export-Csv -NoTypeInformation -delimiter ";" exportsizeBAL_$(get-date -f yyyy-MM-dd_T_HH_mm_ss).csv
```


## Exchange 2019 PowerShell - Move ALL MailBox of a domaine to another DataBase
```
Get-Mailbox -Database <Source_DataBase> -Filter {EmailAddresses -like '*@<Domaine_Name>'} | New-MoveRequest -TargetDatabase <Target_DataBase>
```


## Exchange 2019 PowerShell - Get MoveResquest and filter by TargetDataBase 1
```
Get-MoveRequest | Where-Object { $_.TargetDatabase -eq "<Target_DataBase>" }
```


## Exchange 2019 PowerShell - Get MoveResquest and filter by TargetDataBase 2
```
Get-MoveRequest | Where-Object { $_.TargetDatabase -eq "<Target_DataBase1>" -or $_.TargetDatabase -eq "<Target_DataBase2>" }
```


## Exchange 2019 PowerShell - Get All MailBoxes size + Adresses + ALias and save as csv File
```
Get-MoveRequest | ForEach-Object { $stats = Get-MoveRequestStatistics -Identity $_.Identity; "$($_.TargetMailbox) - Percentage Completion: $($stats.PercentComplete)%" }
```


## Exchange 2019 PowerShell - Get Mailbox Export Request In Failed State
```
Get-MailboxExportRequest | ?{$_.Status -eq "Failed"}
```


## Exchange 2019 PowerShell - Remove  Mailbox Export Request In Failed State
```
Get-MailboxExportRequest -Status Failed | Remove-MailboxExportRequest
```


## Exchange 2019 PowerShell - Get All Disconnected MailBox list
```
Get-MailboxStatistics -Database <Database> | Where-Object {$_.DisconnectDate -ne $null}
```


## Exchange 2019 PowerShell - Get All Disconnected MailBox list By DataBase
```
Get-MailboxDatabase | Get-MailboxStatistics | Where-Object {$_.DisconnectDate -ne $null} | Select-Object DisplayName,MailboxGuid,DisconnectDate,database
```


## Exchange 2019 PowerShell - Get All Disconnected MailBox list
```
Get-MailboxStatistics -Database "<DB_Name>" | Where-Object {$_.DisconnectDate -ne $null} | Select-Object DisplayName,MailboxGuid,DisconnectDate
```


## Exchange 2019 PowerShell - Connect a Disconnected MailBox - MailboxStatistics & _.DisconnectDate
```
        $MailboxGuid = <MailboxGuid>
        $Database = <Database>
        $UserPrincipalName = <Address_Mail>
        $Server = <Server_FQDN>
        Connect-Mailbox -Identity $MailboxGuid -Database $Database -User $UserPrincipalName
```

