# saz-veeam-powershell

#plateform/windows
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/veeam-powershell


## VEEAM PowerShell - Get JOB Info
```
Get-VBRJob -Name <Jobname>
```


## VEEAM PowerShell - Disable JOB Schadule
```
Get-VBRJob -Name <Jobname> | Disable-VBRJobSchedule
```


## VEEAM PowerShell - Enable JOB Schadule
```
Get-VBRJob -Name <Jobname> | Enable-VBRJobSchedule
```


## VEEAM PowerShell - Start JOB Schadule
```
Get-VBRJob -Name <Jobname1>, <Jobname2>, ... | Start-VBRJob
```


## VEEAM PowerShell - Create JOB VCD
```
    #### The RunAsync parameter is set to bring the process to the background.
\$vCloudServer = <vCloud_Server>
Add-VBRvCloudJob -Entity $vCloudServer -Name <vCloud_Job_Name> | Start-VBRJob -RunAsync
```


## VEEAM PowerShell - Stopping Specific Job [Using Pipeline]
```
Get-VBRJob -Name <Jobname> | Stop-VBRJob
```

## VEEAM PowerShell - Stopping Specific Job [Using Variable]
```
\$SharePointFileCopyJob = Get-VBRJob
Stop-VBRJob -Job $SharePointFileCopyJob
```


## VEEAM PowerShell - Remove Job
```
Get-VBRJob -Name <Jobname> | Remove-VBRJob
```



## VEEAM PowerShell - Adding VM to Job by Variable
```
$job = Get-VBRJob
Find-VBRViEntity -Name VM01 | Add-VBRViJobObject -Job $job
```






