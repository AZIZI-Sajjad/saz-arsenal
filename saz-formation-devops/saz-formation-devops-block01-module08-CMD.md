# BAC+3-B01-M08-CMD

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS


## Lister les périphériques PCI détectés
```
lspci
```

## Lister les ports et périphériques USB
```
lsusb
```

## Afficher le nom des périphériques USB via sysfs
```
cat /sys/bus/usb/devices/*/product
```

## Afficher l'inventaire matériel complet
```
lshw
```

## Afficher un résumé lisible du matériel
```
lshw --short
```

## Installer lshw
```
apt install lshw
```

## Filtrer l'inventaire matériel par catégorie
```
lshw -class <Classe>
```

## Afficher l'utilisation de la swap
```
swapon -s
```

## Lister les modules du noyau chargés
```
lsmod
```

## Afficher l'utilisation de la mémoire
```
free
```

## Afficher les messages du noyau
```
dmesg
```

## Consulter les paramètres du noyau
```
sysctl
```

## Afficher la version du système
```
uname
```

## Afficher le temps de fonctionnement du système
```
uptime
```

## Afficher tous les processus de tous les utilisateurs
```
ps -ef
```

## Afficher les processus en temps réel
```
top
```

## Afficher les processus en temps réel (version améliorée)
```
htop
```

## Afficher la hiérarchie des processus
```
pstree [-p]
```

## Identifier un processus par son nom
```
pgrep [-a] <NomProcessus>
```

## Envoyer un signal à un processus par PID
```
kill <NumeroSignal> <PID>
```

## Envoyer un signal à un processus par son nom
```
killall <NumeroSignal> <NomProcessus>
```

## Lancer un processus avec une priorité donnée
```
nice [-n <Niceness>] <Commande> [<Arguments>]
```

## Modifier la priorité d'un processus en cours
```
renice <Niceness> -p <PID>
```

## Éditer un fichier d'unité systemd officiel
```
nano -c /usr/lib/systemd/system/<NomUnite>.service
```

## Vérifier le lien symbolique d'une unité dans une target
```
ll /etc/systemd/system/<NomCible>.target.wants/<NomUnite>.service
```

## Modifier temporairement l'entrée de menu GRUB par défaut
```
GRUB_TIMEOUT=<Timeout>
GRUB_CMDLINE_LINUX="<OptionsNoyau>"
```

## Régénérer la configuration GRUB (Debian)
```
update-grub
```

## Régénérer la configuration GRUB (générique)
```
grub-mkconfig -o /boot/grub/grub.cfg
```

## Démarrer ou arrêter un service
```
systemctl start|stop <NomService>
```

## Redémarrer un service
```
systemctl restart <NomService>
```

## Recharger la configuration d'un service
```
systemctl reload <NomService>
```

## Activer un service au démarrage
```
systemctl enable <NomService>
```

## Désactiver un service au démarrage
```
systemctl disable <NomService>
```

## Vérifier si un service est activé au démarrage
```
systemctl is-enabled <NomService>
```

## Vérifier si un service est actif
```
systemctl is-active <NomService>
```

## Changer de target immédiatement
```
systemctl isolate <NomCible>.target
```

## Définir la target par défaut
```
systemctl set-default <NomCible>.target
```

## Afficher des informations détaillées sur un module
```
modinfo [-p] <NomModule>
```

## Afficher les informations d'un module avec sudo
```
sudo modinfo <NomModule>
```

## Charger ou décharger un module noyau
```
modprobe [-r] <NomModule>
```

## Afficher toutes les informations sur le noyau
```
uname -a
```

## Afficher les détails de version du noyau
```
cat /proc/version
```

## Afficher les informations système et kernel
```
hostnamectl
```

## Afficher les paramètres de démarrage du noyau
```
cat /proc/cmdline
```

## Afficher tous les paramètres noyau configurables
```
sysctl -a
```

## Afficher les messages kernel via systemd
```
journalctl -k
```

## Lister les noyaux installés
```
dpkg --list | grep linux-image
```

## Lister les noyaux disponibles
```
apt search | grep linux-image
```

## Afficher la syntaxe de fdisk
```
fdisk [<options>] <FichierSpecialDisque>
```

## Lancer fdisk en mode interactif sur un disque
```
fdisk <FichierSpecialDisque>
```

## Lister les partitions en mode non interactif
```
fdisk -l
```

## Exécuter une commande parted en mode non interactif
```
parted <Commande> <FichierSpecialDisque>
```

## Lister les partitions du système avec parted
```
parted -l
```

## Lancer parted en mode interactif
```
parted [<FichierSpecialDisque>]
```

## Créer une table de partition GPT avec parted
```
parted <FichierSpecialDisque> mklabel gpt
```

## Créer une partition avec parted
```
parted <FichierSpecialDisque> mkpart <Debut> <Fin>
```

## Créer un ou plusieurs volumes physiques LVM
```
pvcreate <VolumePhysique1> <VolumePhysique2>
```

## Consulter le résumé des volumes physiques
```
pvs [<VolumePhysique>]
```

## Consulter le détail des volumes physiques
```
pvdisplay [<VolumePhysique>]
```

## Créer un groupe de volumes LVM
```
vgcreate <NomGroupeVolumes> <VolumePhysique1> <VolumePhysique2>
```

## Consulter le résumé des groupes de volumes
```
vgs [<GroupeVolumes>]
```

## Consulter le détail des groupes de volumes
```
vgdisplay <GroupeVolumes>
```

## Créer un volume logique LVM
```
lvcreate -L <Taille> -n <NomVolumeLogique> <NomGroupeVolumes>
```

## Consulter le résumé des volumes logiques
```
lvs [<VolumeLogique>]
```

## Consulter le détail des volumes logiques
```
lvdisplay [<VolumeLogique>]
```

## Étendre un groupe de volumes avec un nouveau disque
```
vgextend <NomGroupeVolumes> <VolumePhysique>
```

## Formater une partition (syntaxe avec type)
```
mkfs [<options>] -t <TypeSystemeFichiers> <FichierSpecialPartition>
```

## Formater une partition (syntaxe abrégée)
```
mkfs.<TypeSystemeFichiers> <FichierSpecialPartition>
```

## Formater une partition en ext4 avec l'option type
```
mkfs -t ext4 <FichierSpecialPartition>
```

## Formater une partition en ext4 avec label et réservation
```
mkfs.ext4 -L <Label> [-m <PartRoot>] <FichierSpecialPartition>
```

## Vérifier le type de système de fichiers d'une partition
```
lsblk -f
```

## Afficher le système de fichiers d'une partition avec parted
```
parted <FichierSpecialPartition> print
```

## Monter manuellement un système de fichiers
```
mount <FichierSpecialPartition> <PointMontage>
```

## Lister les systèmes de fichiers montés
```
mount
```

## Monter tous les systèmes de fichiers de /etc/fstab
```
mount -a
```

## Vérifier l'état des systèmes de fichiers montés
```
df -h
```

## Initialiser une partition ou un fichier de swap
```
mkswap [<options>] <FichierSpecialPartition> [<Taille>]
```

## Activer une swap
```
swapon <FichierSpecialPartition>
```

## Désactiver une swap
```
swapoff <FichierSpecialPartition>
```

## Afficher tous les logs disponibles
```
journalctl
```

## Afficher les dernières lignes de logs
```
journalctl -n <NombreLignes>
```

## Aller directement à la fin des logs
```
journalctl -e
```

## Filtrer les logs par service systemd
```
journalctl -u <NomService>
```

## Filtrer les logs sur une période de temps
```
journalctl --since <DateDebut> --until <DateFin>
```

## Filtrer les logs par boot
```
journalctl -b [-x]
```

## Afficher les logs en temps réel
```
journalctl -f
```

## Filtrer les logs par niveau de sévérité
```
journalctl -p <Priorite>
```

## Afficher la crontab d'un utilisateur
```
crontab -l [-u <NomUtilisateur>]
```

## Éditer la crontab d'un utilisateur
```
crontab -e [-u <NomUtilisateur>]
```

## Supprimer la crontab d'un utilisateur
```
crontab -r [-u <NomUtilisateur>]
```

## Vérifier l'état du démon cron
```
systemctl status crond
```

## Éditer le fichier sudoers de manière sécurisée
```
visudo
```

## Exécuter une commande avec sudo
```
sudo <Commande>
```

## Syntaxe d'une règle dans /etc/sudoers
```
<NomUtilisateur> <Hote>=(<Cible>) <Commande>
```

## Autoriser un utilisateur à exécuter reboot
```
<NomUtilisateur> ALL=(root) /sbin/reboot
```

## Lister les droits sudo accordés
```
sudo -l
```

## Afficher les logs des usages de sudo
```
journalctl -t sudo
```

## Mettre à jour le cache local des dépôts
```
apt update
```

## Appliquer les mises à jour disponibles
```
apt upgrade
```

## Installer le mécanisme de mises à jour automatiques
```
apt install unattended-upgrades apt-listchanges
```

## Tester les mises à jour automatiques sans les appliquer
```
unattended-upgrades --dry-run --debug
```