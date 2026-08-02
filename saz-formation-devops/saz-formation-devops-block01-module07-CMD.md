# BAC+3-B01-M07-CMD

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS


## Afficher les adresses IP configurées
```
ip addr
```

## Afficher la table de routage
```
ip route
```

## Tester la connectivité vers une passerelle
```
ping <IP>
```

## Afficher le chemin réseau vers une destination
```
traceroute <IP>
```

## Résoudre un nom DNS
```
nslookup <NomDNS>
```

## Afficher l'état des interfaces réseau
```
ip link
```

## Afficher la table ARP
```
arp -a
```

## Afficher les sockets en écoute avec ports et processus
```
ss -tulpen
```

## Tester la connectivité avec un nombre de paquets défini
```
ping -c <NombrePaquets> <IP>
```

## Afficher la configuration réseau du client Linux
```
cat /etc/resolv.conf
```

## Renouveler le bail DHCP en mode verbeux (client Linux)
```
sudo dhclient -v
```

## Afficher la configuration IP complète (client Windows)
```
ipconfig /all
```

## Libérer le bail DHCP (client Windows)
```
ipconfig /release
```

## Renouveler le bail DHCP (client Windows)
```
ipconfig /renew
```

## Mettre à jour la liste des paquets
```
sudo apt update
```

## Installer le serveur DHCP ISC
```
sudo apt install isc-dhcp-server -y
```

## Éditer l'interface d'écoute du serveur DHCP
```
sudo nano /etc/default/isc-dhcp-server
```

## Définir l'interface d'écoute IPv4 du serveur DHCP
```
INTERFACESv4="<Interface>"
```

## Éditer la configuration principale du serveur DHCP
```
sudo nano /etc/dhcp/dhcpd.conf
```

## Configuration d'une plage DHCP (dhcpd.conf)
```
default-lease-time 600;
max-lease-time 7200;
authoritative;

subnet <Reseau> netmask <Masque> {
  range <IPDebut> <IPFin>;
  option routers <Passerelle>;
  option subnet-mask <Masque>;
  option domain-name-servers <DNS1>, <DNS2>;
  option domain-name "<NomDomaine>";
}
```

## Réservation DHCP par adresse MAC (dhcpd.conf)
```
host <NomHote> {
  hardware ethernet <AdresseMAC>;
  fixed-address <IPReservee>;
}
```

## Redémarrer le serveur DHCP ISC
```
sudo systemctl restart isc-dhcp-server
```

## Vérifier l'état du serveur DHCP ISC
```
sudo systemctl status isc-dhcp-server
```

## Suivre les logs du serveur DHCP ISC en temps réel
```
sudo journalctl -u isc-dhcp-server -f
```

## Libérer le bail DHCP (client Linux)
```
sudo dhclient -r
```

## Installer le rôle DHCP (PowerShell)
```
Install-WindowsFeature DHCP -IncludeManagementTools
```

## Créer une étendue DHCP IPv4 (PowerShell)
```
Add-DhcpServerv4Scope `
  -Name "<NomEtendue>" `
  -StartRange <IPDebut> `
  -EndRange <IPFin> `
  -SubnetMask <Masque>
```

## Configurer les options d'une étendue DHCP (PowerShell)
```
Set-DhcpServerv4OptionValue `
  -ScopeId <IdEtendue> `
  -Router <Passerelle> `
  -DnsServer <DNS> `
  -DnsDomain "<NomDomaine>"
```

## Activer une étendue DHCP (PowerShell)
```
Set-DhcpServerv4Scope -ScopeId <IdEtendue> -State Active
```

## Lister les étendues DHCP IPv4 (PowerShell)
```
Get-DhcpServerv4Scope
```

## Lister les baux DHCP d'une étendue (PowerShell)
```
Get-DhcpServerv4Lease -ScopeId <IdEtendue>
```

## Configuration DHCP sur routeur Cisco IOS
```
conf t

ip dhcp excluded-address <IPDebutExclue> <IPFinExclue>

ip dhcp pool <NomPool>
 network <Reseau> <Masque>
 default-router <Passerelle>
 dns-server <DNS1> <DNS2>
 domain-name <NomDomaine>
 lease <NombreJours>

interface <Interface>
 ip address <IP> <Masque>
 no shutdown

end
write memory
```

## Afficher les pools DHCP (Cisco)
```
show ip dhcp pool
```

## Afficher les baux DHCP attribués (Cisco)
```
show ip dhcp binding
```

## Afficher la configuration DHCP en cours (Cisco)
```
show running-config | section dhcp
```

## Tester la résolution inverse et le domaine (client Windows)
```
nslookup <NomDomaine>
```

## Tester une ressource web via HTTP (en-têtes seuls)
```
curl -I http://<NomDNS>
```

## Tester une ressource web via HTTPS sans vérif certificat
```
curl -k -I https://<NomDNS>
```

## Filtrer les sockets sur les ports web
```
ss -tulpen | grep -E ':80|:443'
```

## Établir une session TLS avec un serveur web
```
openssl s_client -connect <NomDNS>:443 -servername <NomDNS>
```

## Installer Bind9 et les utilitaires DNS
```
sudo apt install bind9 bind9utils dnsutils -y
```

## Éditer la déclaration des zones locales Bind9
```
sudo nano /etc/bind/named.conf.local
```

## Déclarer une zone maître Bind9
```
zone "<NomZone>" {
    type master;
    file "<CheminFichierZone>";
};
```

## Créer un fichier de zone à partir du modèle
```
sudo cp /etc/bind/db.local <CheminFichierZone>
```

## Éditer le fichier de zone Bind9
```
sudo nano <CheminFichierZone>
```

## Contenu d'un fichier de zone Bind9
```
$TTL    604800
@       IN      SOA     ns1.<NomZone>. admin.<NomZone>. (
                              2
                         604800
                          86400
                        2419200
                         604800 )

@       IN      NS      ns1.<NomZone>.
ns1     IN      A       <IPns1>
www     IN      A       <IPwww>
files   IN      A       <IPfiles>
```

## Vérifier la syntaxe de la configuration Bind9
```
sudo named-checkconf
```

## Vérifier la syntaxe d'un fichier de zone
```
sudo named-checkzone <NomZone> <CheminFichierZone>
```

## Redémarrer le service Bind9
```
sudo systemctl restart bind9
```

## Vérifier l'état du service Bind9
```
sudo systemctl status bind9
```

## Tester la résolution via un serveur DNS précis
```
nslookup <NomDNS> <IPServeurDNS>
```

## Interroger un serveur DNS avec dig
```
dig @<IPServeurDNS> <NomDNS>
```

## Installer le rôle DNS (PowerShell)
```
Install-WindowsFeature DNS -IncludeManagementTools
```

## Créer une zone DNS primaire (PowerShell)
```
Add-DnsServerPrimaryZone `
  -Name "<NomZone>" `
  -ZoneFile "<NomFichierZone>"
```

## Ajouter un enregistrement A (PowerShell)
```
Add-DnsServerResourceRecordA `
  -ZoneName "<NomZone>" `
  -Name "<NomHote>" `
  -IPv4Address "<IP>"
```

## Lister les zones DNS (PowerShell)
```
Get-DnsServerZone
```

## Lister les enregistrements d'une zone DNS (PowerShell)
```
Get-DnsServerResourceRecord -ZoneName "<NomZone>"
```

## Résoudre un nom via un serveur DNS précis (PowerShell)
```
Resolve-DnsName <NomDNS> -Server <IPServeurDNS>
```

## Interroger un nom DNS avec dig
```
dig <NomDNS>
```

## Résoudre un nom DNS (PowerShell)
```
Resolve-DnsName <NomDNS>
```

## Installer le serveur NFS (noyau)
```
sudo apt install nfs-kernel-server -y
```

## Créer un répertoire partagé NFS
```
sudo mkdir -p <CheminPartage>
```

## Attribuer le propriétaire nobody au partage NFS
```
sudo chown nobody:nogroup <CheminPartage>
```

## Définir les permissions du partage NFS
```
sudo chmod 0777 <CheminPartage>
```

## Éditer le fichier des exports NFS
```
sudo nano /etc/exports
```

## Déclarer un export NFS
```
<CheminPartage> <Reseau>(rw,sync,no_subtree_check)
```

## Recharger la table des exports NFS
```
sudo exportfs -ra
```

## Afficher les exports NFS actifs
```
sudo exportfs -v
```

## Redémarrer le serveur NFS
```
sudo systemctl restart nfs-kernel-server
```

## Vérifier l'état du serveur NFS
```
sudo systemctl status nfs-kernel-server
```

## Installer le client NFS
```
sudo apt install nfs-common -y
```

## Créer le point de montage NFS côté client
```
sudo mkdir -p <PointMontage>
```

## Monter un partage NFS distant
```
sudo mount -t nfs <IPServeur>:<CheminPartage> <PointMontage>
```

## Vérifier un montage NFS
```
df -h | grep partage
```

## Filtrer les montages NFS
```
mount | grep nfs
```

## Déclarer un montage NFS permanent (fstab)
```
<IPServeur>:<CheminPartage> <PointMontage> nfs defaults,_netdev 0 0
```

## Créer un dossier partagé (PowerShell)
```
New-Item -ItemType Directory -Path "<CheminDossier>"
```

## Créer un partage SMB (PowerShell)
```
New-SmbShare `
  -Name "<NomPartage>" `
  -Path "<CheminDossier>" `
  -FullAccess "<GroupeAccesTotal>" `
  -ChangeAccess "<GroupeAccesModification>"
```

## Lister les partages SMB (PowerShell)
```
Get-SmbShare
```

## Afficher les droits d'accès d'un partage SMB (PowerShell)
```
Get-SmbShareAccess -Name "<NomPartage>"
```

## Connecter un lecteur réseau SMB (client Windows)
```
net use <Lettre>: \\<Serveur>\<NomPartage>
```

## Installer Samba et le client smbclient
```
sudo apt install samba smbclient -y
```

## Créer un dossier partagé Samba
```
sudo mkdir -p <CheminPartage>
```

## Définir les permissions du dossier Samba
```
sudo chmod 2770 <CheminPartage>
```

## Attribuer le propriétaire du dossier Samba
```
sudo chown root:sambashare <CheminPartage>
```

## Créer un utilisateur système sans shell pour Samba
```
sudo useradd -M -s /usr/sbin/nologin <NomUtilisateur>
```

## Ajouter un utilisateur à Samba
```
sudo smbpasswd -a <NomUtilisateur>
```

## Activer un utilisateur Samba
```
sudo smbpasswd -e <NomUtilisateur>
```

## Éditer la configuration Samba
```
sudo nano /etc/samba/smb.conf
```

## Déclarer un partage Samba (smb.conf)
```
[<NomPartage>]
   path = <CheminPartage>
   browsable = yes
   read only = no
   guest ok = no
   valid users = <NomUtilisateur>
   create mask = 0660
   directory mask = 2770
```

## Vérifier la configuration Samba
```
testparm
```

## Redémarrer les services Samba
```
sudo systemctl restart smbd nmbd
```

## Vérifier l'état du service Samba
```
sudo systemctl status smbd
```

## Lister les partages Samba d'un serveur
```
smbclient -L //<Serveur> -U <NomUtilisateur>
```

## Se connecter à un partage Samba
```
smbclient //<Serveur>/<NomPartage> -U <NomUtilisateur>
```

## Lister les exports NFS d'un serveur
```
showmount -e <Serveur>
```

## Installer Chrony
```
sudo apt install -y chrony
```

## Afficher l'état de l'heure système
```
timedatectl
```

## Afficher l'état de synchronisation Chrony
```
chronyc tracking
```

## Lister les sources NTP Chrony
```
chronyc sources -v
```

## Vérifier l'état du service Chrony
```
systemctl status chrony
```

## Activer Chrony au démarrage
```
systemctl enable chrony
```

## Redémarrer le service Chrony
```
systemctl restart chrony
```

## Éditer la configuration Chrony
```
sudo nano /etc/chrony/chrony.conf
```

## Autoriser un réseau à interroger le serveur NTP (chrony.conf)
```
allow <Reseau>
```

## Déclarer un serveur NTP source (chrony.conf)
```
server <IPServeurNTP> iburst
```

## Autoriser le port NTP dans le pare-feu ufw
```
sudo ufw allow 123/udp
```

## Vérifier l'état du service de temps Windows
```
w32tm /query /status
```

## Afficher la source de temps Windows
```
w32tm /query /source
```

## Forcer la resynchronisation du temps Windows
```
w32tm /resync
```

## Configurer une source NTP manuelle (Windows)
```
w32tm /config /manualpeerlist:"<IPServeurNTP>" /syncfromflags:manual /reliable:no /update
```

## Arrêter le service de temps Windows
```
net stop w32time
```

## Démarrer le service de temps Windows
```
net start w32time
```

## Vérifier que le serveur écoute sur le port NTP
```
sudo ss -lunp | grep ':123'
```

## Afficher les informations système (Windows)
```
systeminfo
```

## Afficher le nom de la machine (Windows)
```
hostname
```

## Lister les rôles et fonctionnalités Windows
```
Get-WindowsFeature
```

## Installer une fonctionnalité Windows par nom
```
Install-WindowsFeature -Name <NomRole>
```

## Renommer le serveur et redémarrer (PowerShell)
```
Rename-Computer -NewName "<NomServeur>" -Restart
```

## Lister les cartes réseau (PowerShell)
```
Get-NetAdapter
```

## Afficher la configuration IP détaillée (PowerShell)
```
Get-NetIPConfiguration
```

## Configurer une adresse IP fixe (PowerShell)
```
New-NetIPAddress -InterfaceAlias "<Interface>" -IPAddress <IP> -PrefixLength <Prefixe> -DefaultGateway <Passerelle>
```

## Configurer les serveurs DNS d'une interface (PowerShell)
```
Set-DnsClientServerAddress -InterfaceAlias "<Interface>" -ServerAddresses <DNS>
```

## Tester la connectivité vers une cible (PowerShell)
```
Test-Connection <IP>
```

## Résoudre un nom externe (PowerShell)
```
Resolve-DnsName <NomDNS>
```

## Installer le rôle AD DS (PowerShell)
```
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```

## Importer le module Active Directory (PowerShell)
```
Import-Module ActiveDirectory
```

## Lister tous les utilisateurs AD
```
Get-ADUser -Filter *
```

## Lister tous les ordinateurs AD
```
Get-ADComputer -Filter *
```

## Lister tous les groupes AD
```
Get-ADGroup -Filter *
```

## Afficher un utilisateur AD avec des propriétés précises
```
Get-ADUser <NomCompte> -Properties mail,department,accountExpires
```

## Créer une nouvelle forêt AD (PowerShell)
```
Install-ADDSForest `
  -DomainName "<NomDomaine>" `
  -DomainNetbiosName "<NomNetbios>" `
  -InstallDns `
  -SafeModeAdministratorPassword (Read-Host -AsSecureString "Mot de passe DSRM") `
  -Force
```

## Afficher les informations du domaine AD
```
Get-ADDomain
```

## Afficher les informations de la forêt AD
```
Get-ADForest
```

## Lister les contrôleurs de domaine
```
Get-ADDomainController -Filter *
```

## Diagnostiquer l'état du contrôleur de domaine
```
dcdiag
```

## Créer un utilisateur AD (PowerShell)
```
New-ADUser -Name "<NomComplet>" -SamAccountName <NomCompte> -UserPrincipalName <NomCompte>@<NomDomaine> -Enabled $true
```

## Créer un groupe AD global de sécurité (PowerShell)
```
New-ADGroup -Name "<NomGroupe>" -GroupScope Global -GroupCategory Security
```

## Ajouter un utilisateur à un groupe AD
```
Add-ADGroupMember -Identity "<NomGroupe>" -Members <NomCompte>
```

## Autoriser un serveur DHCP dans Active Directory
```
Add-DhcpServerInDC -DnsName "<NomDNSServeur>" -IPAddress <IP>
```

## Lister les serveurs DHCP autorisés dans AD
```
Get-DhcpServerInDC
```

## Configurer la passerelle d'une étendue DHCP (PowerShell)
```
Set-DhcpServerv4OptionValue -ScopeId <IdEtendue> -Router <Passerelle>
```

## Configurer le DNS et le domaine d'une étendue DHCP (PowerShell)
```
Set-DhcpServerv4OptionValue -ScopeId <IdEtendue> -DnsServer <DNS> -DnsDomain "<NomDomaine>"
```

## Exporter la configuration DHCP (PowerShell)
```
Export-DhcpServer -ComputerName "<NomServeur>" -File "<CheminFichier>" -Leases -Force
```

## Importer la configuration DHCP (PowerShell)
```
Import-DhcpServer -ComputerName "<NomServeur>" -File "<CheminFichier>" -Leases -BackupPath "<CheminBackup>" -Force
```

## Tester les enregistrements SRV du domaine (client)
```
nslookup -type=SRV _ldap._tcp.dc._msdcs.<NomDomaine>
```

## Joindre une machine à un domaine AD (PowerShell)
```
Add-Computer -DomainName "<NomDomaine>" -Credential "<Domaine>\<Administrateur>" -Restart
```

## Afficher l'utilisateur connecté (Windows)
```
whoami
```

## Afficher le domaine de la machine (Windows)
```
systeminfo | findstr /B /C:"Domaine"
```

## Vérifier le contrôleur de domaine trouvé par le client
```
nltest /dsgetdc:<NomDomaine>
```

## Rechercher un ordinateur AD par identité
```
Get-ADComputer -Identity <NomMachine>
```

## Déplacer un objet AD vers une OU
```
Move-ADObject -Identity "<DNObjet>" -TargetPath "<DNCibleOU>"
```

## Créer un partage SMB avec droits par groupe (PowerShell)
```
New-SmbShare -Name "<NomPartage>" -Path "<CheminDossier>" -FullAccess "<Domaine>\<GroupeModification>" -ReadAccess "<Domaine>\<GroupeLecture>"
```

## Afficher les droits NTFS d'un dossier
```
icacls "<CheminDossier>"
```

## Ajouter un droit de modification NTFS à un groupe
```
icacls "<CheminDossier>" /grant "<Domaine>\<GroupeModification>:(OI)(CI)M"
```

## Ajouter un droit de lecture NTFS à un groupe
```
icacls "<CheminDossier>" /grant "<Domaine>\<GroupeLecture>:(OI)(CI)RX"
```

## Forcer l'application des stratégies de groupe
```
gpupdate /force
```

## Afficher les stratégies de groupe appliquées
```
gpresult /r
```