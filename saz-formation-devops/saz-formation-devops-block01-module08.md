# BAC+3-B01-M08-FC

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS

## initramfs
```
Système de fichiers temporaire chargé en RAM au démarrage, contenant les drivers et outils nécessaires pour monter le vrai système de fichiers racine. Il permet le déverrouillage LUKS, l'assemblage RAID/LVM, etc.
```

## journalctl
```
Commande pour interroger les logs collectés par systemd-journald. journalctl offre des capacités de filtrage avancées (par service, date, niveau de sévérité, boot, etc.).
```

## SysFS (/sys)
```
Pseudo système de fichiers exposant la hiérarchie des périphériques, drivers et informations du noyau. Organisé par bus, classe de périphériques, il permet également la configuration de certains paramètres système.
```

## DevFS (/dev)
```
Système de fichiers virtuel contenant les fichiers spéciaux représentant les périphériques matériels (disques, terminaux, etc.). Il est géré dynamiquement par udev sous Linux moderne.
```

## ext4
```
Système de fichiers journalisé, évolution de ext3. C'est le système de fichiers par défaut sur de nombreuses distributions Linux. Il est fiable, performant et largement supporté.
```

## BIOS/UEFI
```
Firmware qui initialise le matériel au démarrage de l'ordinateur. Le BIOS (Basic Input/Output System) est l'ancien standard, tandis que l'UEFI (Unified Extensible Firmware Interface) est la version moderne offrant notamment le support des disques de plus de 2 To.
```

## swap
```
La swap est une zone d’échange : quand la RAM commence à manquer, le noyau peut déplacer des pages mémoire peu utilisées vers le disque (swap partition ou swap file) pour libérer de la RAM.
```

## Démon (Daemon)
```
Application qui s'exécute en arrière-plan sans interaction directe avec l'utilisateur. Exemples : sshd (serveur SSH), httpd (serveur web), systemd-journald (gestion des logs).
```

## ProcFS (/proc)
```
Pseudo système de fichiers exposant en temps réel des informations sur les processus et l'état du système (mémoire, CPU, noyau). Il est présent uniquement en mémoire, pas sur disque.
```

## GRUB (Grand Unified Bootloader)
```
Bootloader standard sous Linux. Il permet de sélectionner le système à démarrer, charge le noyau et l'initramfs, et peut passer des paramètres au noyau. La configuration se fait dans /etc/default/grub.
```

## GPT (GUID Partition Table)
```
Standard moderne de partitionnement remplaçant le MBR. GPT supporte les disques de plus de 2 To, permet un grand nombre de partitions et offre une meilleure sécurisation des données grâce à la redondance.
```

## hostnamectl
```
Commande systemd qui sert à afficher et modifier le nom de la machine (hostname), et quelques infos système (châssis, OS, kernel…), de façon persistante.
```

## Montage d'un système de fichiers
```
Action de rattacher un périphérique/partition (ou un partage réseau, une image disque, etc.) à un dossier (point de montage) pour accéder à son contenu.
```

## MBR (Master Boot Record)
```
Ancien standard de partitionnement situé dans le premier secteur du disque. Limité à 4 partitions primaires et des disques de 2 To maximum, il est remplacé progressivement par GPT.
```

## LVM (Logical Volume Manager)
```
Système de gestion du stockage en 3 couches : Physical Volume (PV), Volume Group (VG) et Logical Volume (LV). LVM permet de s'affranchir des limites physiques des disques et d'effectuer des opérations de redimensionnement à chaud.
```

## Bootloader
```
Programme responsable du chargement du système d'exploitation. Sous Linux, GRUB (Grand Unified Bootloader) est le bootloader le plus couramment utilisé. Il charge le noyau et l'initramfs en mémoire.
```

## dmesg
```
Commande permettant d'afficher le tampon des messages du noyau Linux. dmesg est utile pour diagnostiquer les problèmes matériels et voir les messages de démarrage du système.
```

## Cron
```
Démon système qui exécute des commandes ou scripts à des horaires définis. Il permet l'automatisation de tâches récurrentes. La configuration se fait via des fichiers crontab (utilisateur ou système).
```

## Signal
```
Message envoyé à un processus pour contrôler son comportement. Principaux signaux : SIGTERM (15) pour arrêt propre, SIGKILL (9) pour arrêt forcé, SIGINT (2) pour interruption (Ctrl+C).
```

## nice
```
nice sert à lancer une commande avec une priorité CPU plus ou moins élevée, en jouant sur la niceness d’un processus
```

## Target
```
Type d'unité systemd regroupant d'autres unités pour définir un état du système. Exemples : graphical.target (interface graphique complète), multi-user.target (système console), rescue.target (mode dépannage).
```

## Point de montage
```
Dossier dans l’arborescence, sur lequel on “accroche” un système de fichiers (disque, partition, clé USB, partage réseau, ISO…).
```

## Processus
```
Programme en cours d'exécution avec son contexte (mémoire, fichiers ouverts, droits). Un processus est caractérisé par un PID, un propriétaire (UID), un état (running, sleeping, stopped, zombie) et des ressources (CPU, RAM).
```

## PID (Process ID)
```
Identifiant numérique unique attribué à chaque processus par le système. Le PID 1 est toujours systemd (ou init). Le PPID (Parent PID) identifie le processus parent.
```

## Service
```
Démon géré par systemd, facilitant son administration (démarrage, arrêt, redémarrage automatique, logs). Il est décrit par un fichier unit (.service) dans /usr/lib/systemd/system/ ou /etc/systemd/system/.
```

## Udev
```
Gestionnaire de périphériques dynamique fusionné avec systemd. I crée et gère les fichiers de périphériques dans /dev, applique des règles de nommage et de configuration au branchement/détection de matériel.
```

## Kernel (Noyau)
```
Cœur du système d'exploitation Linux. Le kernel gère les ressources matérielles, l'ordonnancement des processus, la mémoire, les systèmes de fichiers et la communication réseau. Stocké dans /boot.
```

## systemctl
```
Commande principale pour interagir avec systemd. systemctl permet de démarrer/arrêter/redémarrer des services, les activer/désactiver au boot, vérifier leur état, et gérer le système (reboot, poweroff).
```

## systemd
```
Système d'initialisation moderne (PID 1) qui remplace init. systemd gère le démarrage/arrêt des services, les dépendances, les logs (journald), les montages, les timers, etc. Il se base sur des unit files.
```

