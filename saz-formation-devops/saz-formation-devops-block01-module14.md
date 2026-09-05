# BAC+3-B01-M14-FC

#plateform/VISIPLUS  
#target/local  
#cat/PRIVESC  
#cat/PERSIST  
#cat/AZIZI-Sajjad  
#tag/DEVOPS

## SIEM (Security Information and Event Management)

```text
Outil combinant la collecte, l’analyse et la corrélation des logs pour la sécurité.
```

## VPN (Virtual Private Network)

```text
Connexion chiffrée entre deux points pour sécuriser les communications.
```

## NTP

```text
Network Time Protocol

Protocole permettant de distribuer l'heure auprès des différents clients.
```

## Reverse Proxy

```text
Proxy placé côté serveur, gérant les connexions entrantes.
```

## VLAN

```text
Virtual Local Area Networks

Protocole permettant de segmenter des réseaux physiques en sous-réseaux logiques.
```

## Hash / empreinte

```text
C'est une fonction de hashage qui permet de vérifier le caractère identique d'un fichier.
```

## DHCP

```text
Dynamic Host Configuration Protocol

Protocole permettant de distribuer des adresses IP à des hôtes.
```

## AGDLP

```text
Méthodologie pour gérer les droits d’accès dans Active Directory.
```

## Proxy

```text
Service qui est utilisé comme intermédiaire entre un client et une ressource (exemple entre un poste client et un site web).
```

## AppLocker

```text
Outil Microsoft permettant de restreindre l'exécution de programmes.
```

## CARP

```text
Common Address Redundancy Protocol

Cela permet à des hôtes sur un même réseau d'utiliser une adresse IP virtuelle dans un cadre de haute disponibilité.
```

## VPN

```text
Réseau privé virtuel

Protocole permettant de créer une connexion sécurisée entre un appareil et un réseau privé via le réseau Internet.
```

## TPM

```text
Trusted Platform Module

Une puce TPM est un processeur de chiffrement sécurisé conçu pour effectuer des opérations de chiffrement.
```

## Authentification forte (MFA)

```text
Méthode nécessitant au moins deux moyens de vérification (mot de passe + code SMS, etc.).
```

## SSH

```text
Secure Shell

Protocole qui permet aux administrateurs de se connecter à distance sur des équipements et/ou des machines.
```

## NSX

```text
Pare-feu permettant de mettre en œuvre la micro-segmentation au niveau des machines virtuelles.
```

## Chiffrement

```text
Transformation d’un message pour le rendre illisible sans clé.
```

## NTFS

```text
New Technology File System

Système de fichiers pour les systèmes d'exploitation Microsoft.
```

## VIP (Virtual IP)

```text
Adresse IP virtuelle partagée par plusieurs équipements pour la redondance.
```

## PKI

```text
Public Key Infrastructure

Permet de gérer de manière sécurisée les demandes et le cycle de vie des certificats.
```

## Règle de filtrage

```text
Instruction définissant quel type de trafic est autorisé ou bloqué.
```

## Trunk

```text
Lien réseau transportant plusieurs VLANs.
```

## IPS

```text
Intrusion Prevention System

En plus de surveiller le trafic réseau, il permet d'agir en amont et de bloquer la source d'une potentielle attaque.
```

## IDS

```text
Intrusion Detection System

Un IDS surveille le trafic réseau et remonte des activités suspectes.
```

## PVLAN (Private VLAN)

```text
VLAN subdivisé pour isoler certains équipements.
```

## BitLocker

```text
BitLocker est une fonction de chiffrement de disque intégrée aux versions professionnelles et intégrales de Windows. Il se base sur une puce TPM.
```

## DNS

```text
Domain Name System

Protocole permettant de traduire un nom en adresse IP (ou une IP en nom de domaine).
```

## NAT

```text
Network Address Translation

Processus de translation d'adresse permettant de traduire les adresses IP externes et internes.
```

## LDAP (Lightweight Directory Access Protocol)

```text
Protocole permettant d’interroger et de modifier un annuaire d’entreprise (utilisateurs, groupes…).
```

## RADIUS

```text
Protocole qui gère les autorisations et les authentifications des utilisateurs sur un réseau (exemple : portail captif Wi-Fi).
```

## Redondance

```text
Présence d’un système de secours pour éviter les interruptions.
```

## SNMP (Simple Network Management Protocol)

```text
Protocole utilisé pour superviser les équipements réseau.
```


## Les bonnes pratiques pour notre pare-feu – C04
```
1. Créer des comptes nominatifs

2. Protéger le compte administrateur local

3. Limiter l’administration par SSH

4. Mettre en œuvre l’authentification via certificat

5. Configurer la limitation des tentatives

6. Créer une politique de mot de passe fort

7. Activer le 2FA

8. Ajuster les droits d’administration

9. Définir les sous-réseaux d’administration

10. Désactiver les interfaces inutiles

11. Utiliser une langue comprise par les exploitants

12. Appliquer les mises à jour régulièrement

13. Sauvegarder régulièrement la configuration

14. Création de règles explicites pour le filtrage

15. Superviser notre pare-feu

16. Définir une politique de journalisation

17. Configurer le serveur de temps

18. Privilégier la diversification technologique des pares-feux
```