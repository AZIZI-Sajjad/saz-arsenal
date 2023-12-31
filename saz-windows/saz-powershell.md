# saz-powershell

#plateform/windows
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/SAJJAD
#tag/curl

## PowerShell - Get FQDN 1
[System.Net.Dns]::GetHostByName($env:computerName)

## PowerShell - Get FQDN 2
[System.Net.Dns]::GetHostByName($env:computerName).HostName

## PowerShell - Get FQDN 3
(Get-WmiObject win32_computersystem).DNSHostName+"."+(Get-WmiObject win32_computersystem).Domain

## PowerShell - Get FQDN Remote PC
[System.Net.Dns]::GetHostByName('IP_OR-DNS_NAME')

## PowerShell - Lancer Windows update
control update

## PowerShell - Restart Logs 1/2
Get-WinEvent -ProviderName Microsoft-Windows-Kernel-boot -MaxEvents 1000 | Where-Object {$_.id -eq "25"}

## PowerShell - Restart Logs 2/2
Get-WinEvent -ProviderName Microsoft-Windows-Kernel-boot -MaxEvents 1000 | Where-Object {$_.id -eq "27"}

## PowerShell - Get all Services:
Get-Service

## PowerShell - Get Services Filter
Get-Service | findstr <key_word>

## PowerShell - Get un service 
Get-Service -Name <service_name>

## PowerShell - Activate a service 
Set-Service -Name <service_name> -StartupType Automatic

## PowerShell - Start a service 
Start-Service -Name <service_name>

## PowerShell - Get Services that name start with a keyWord
\$service = <key_word>; while ($true) { cls; Get-Service -DisplayName 'Veeam*' | Get-Service; Start-Sleep -Seconds 1 }

## PowerShell - Get system Informations {{ WindowsProductName }}, {{ WindowsVersion }}, {{ OsHardwareAbstractionLayer }}
Get-ComputerInfo | select WindowsProductName, WindowsVersion, OsHardwareAbstractionLayer

## PowerShell - Get Windows Release ID {{ Build }}
(Get-ItemProperty "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion").ReleaseId

## PowerShell - Get Windows Version
(Get-CimInstance Win32_OperatingSystem).version

## PowerShell - Get Windows Name & Version 
(Get-ItemProperty "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion").ProductName

## PowerShell - Get Installed Windows Rules and Services
Get-WindowsFeature | Where-Object {$_.InstallState -eq 'Installed'}
<!-- # Réf: https://redmondmag.com/articles/2018/10/31/powershell-windows-server-roles-features.aspx -->

<!-- ## PowerShell - À VÉRIFIER
Get-WindowsFeature -Vhd 'F:\VMs\DC\Virtual Hard Disks\DC.vhdx' | Where-Object{$_.InstallState -eq 'Installed'} -->

## PowerShell - Send HTTP/HTTPS Resquest (CURL) - Page Content + Header
Invoke-WebRequest -Uri "http://ifconfig.me/ip" -UseBasicParsing

## PowerShell - Send HTTP/HTTPS Resquest (CURL) - Page Content
Invoke-WebRequest -Uri "http://ifconfig.me/ip" -UseBasicParsing | Select-Object -ExpandProperty Content

## PowerShell - Get PowerShell Version 1
\$PSVersionTable

## PowerShell - Get PowerShell Version 2
Write-Host "PowerShell Version: $($PSVersionTable.PSVersion.Major).$($PSVersionTable.PSVersion.Minor)"
Write-Host "PSCompatibleVersions: $($PSVersionTable.PSCompatibleVersions -join ', ')"
Write-Host "CLRVersion: $($PSVersionTable.CLRVersion)"
Write-Host "BuildVersion: $($PSVersionTable.BuildVersion)"
Write-Host "WSManStackVersion: $($PSVersionTable.WSManStackVersion)"
Write-Host "PSRemotingProtocolVersion: $($PSVersionTable.PSRemotingProtocolVersion)"
Write-Host "SerializationVersion: $($PSVersionTable.SerializationVersion)"

## PowerShell - Test Network Conenction (Network Socket PI:PORT)
Test-NetConnection -ComputerName <IP> -Port <port>

## PowerShell - CMD - Route Print with Filter
route print | findstr <Net_ID_Or_IP_Or_A_Part_Of_Them>

## PowerShell - CMD - Get Net Infos
ipconfig

## PowerShell - CMD - Get All Net Infos
ipconfig /all

## PowerShell - CMD - Get Net IPv4
ipconfig | findstr IPv4

## PowerShell - CMD - Get Net IPv6
ipconfig | findstr IPv6
