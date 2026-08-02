# BAC+3-B01-M06-CMD

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS



## Lister les snapshots d'une VM VirtualBox
```
VBoxManage snapshot "<NomMachineVirtuelle>" list
```

## Créer une VM avec OpenStack CLI
```
openstack <service> <action> [options]
```

## Déployer une VM complète avec OpenStack CLI
```
openstack server create --image <NomImage> \
--flavor <Flavor> --network <NomReseau> \
--key-name <NomCle> --security-group <GroupeSecurite> \
<NomMachineVirtuelle>
```

## Générer une paire de clés SSH
```
ssh-keygen -t ed25519 -C "<Commentaire>"
```

## Copier la clé publique sur le serveur distant
```
ssh-copy-id <NomUtilisateur>@<Serveur>
```

## Tester la connexion SSH
```
ssh <NomUtilisateur>@<Serveur>
```

## Inventaire Ansible avec groupes et groupe parent
```
[load-balancers]
lb1-srv
lb2-srv

[web-servers]
app1-srv
app2-srv

[db-masters]
db1-srv

[db-slaves]
db2-srv

[db-servers:children]
db-masters
db-slaves
```

## Tester la connexion SSH avec les machines (module ping)
```
ansible -i <FichierInventaire> all -m ping
```

## Lister les membres d'un groupe sans se connecter
```
ansible -i <FichierInventaire> <NomGroupe> --list-hosts
```

## Collecter les facts des machines (module setup)
```
ansible -i <FichierInventaire> all -m setup
```

## Fichier ansible.cfg de configuration
```
[defaults]
force_color = 1
inventory = inventories/inv.ini
```

## Syntaxe générale d'une commande ad hoc Ansible
```
ansible -i <FichierInventaire> <Filtre> -a "<Commande>"
```

## Lancer la commande hostname sur toutes les machines
```
ansible -i <FichierInventaire> all -a "hostname"
```

## Lancer une commande en élévation de privilèges (become)
```
ansible -i <FichierInventaire> all -b -a "<Commande>"
```

## Installer un rôle depuis Ansible Galaxy
```
ansible-galaxy install <Auteur>.<NomRole>
```

## Installer une collection depuis Ansible Galaxy
```
ansible-galaxy collection install <Namespace>.<NomCollection>
```

## Lancer un playbook Ansible
```
ansible-playbook -i <FichierInventaire> <NomPlaybook>.yml
```

## Lancer un playbook en mode verbeux
```
ansible-playbook -i <FichierInventaire> <NomPlaybook>.yml -v
```

## Créer les instances de test Molecule
```
molecule create
```

## Détruire les instances de test Molecule
```
molecule destroy
```

## Vérifier un rôle avec Molecule
```
molecule verify
```

## Vérifier la syntaxe d'un rôle avec Molecule
```
molecule lint
```