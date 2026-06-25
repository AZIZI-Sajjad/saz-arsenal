# BAC+3-B01-M06-FC

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS

# FLASHCARDS:



## Ansible
```
Ansible est un outil d’automatisation open source permettant de configurer des serveurs, déployer des applications et orchestrer des infrastructures.
```



## Cloud Computing
```
Modèle fournissant à la demande des ressources informatiques (VMs, stockage, réseau) via Internet ou un réseau privé, avec automatisation, élasticité et facturation à l’usage.
```



## Handler Ansible
```
Tâche déclenchée uniquement lorsqu’un changement est détecté (ex. redémarrer un service après modification d’un fichier de configuration).
```



## Hyperviseur
```
Logiciel assurant la gestion des ressources entre les machines virtuelles. Il répartit CPU, RAM, stockage et isole les VMs les unes des autres.
```



## Hyperviseur Type 1 (Bare-metal)
```
Hyperviseur fonctionnant directement sur le matériel, sans OS intermédiaire. Très performant, utilisé dans les infrastructures professionnelles (ESXi, Hyper-V Server).
```



## Hyperviseur Type 2 (Hosted)
```
Logiciel de virtualisation installé au-dessus d’un OS existant. Idéal pour l’apprentissage et les tests (VirtualBox, VMware Workstation).
```



## Hôte physique (Host)
```
Machine réelle qui fournit les ressources matérielles — processeur, mémoire, stockage, réseau — aux machines virtuelles qui y sont exécutées.
```



## Infrastructure on-premise
```
Infrastructure informatique installée et exploitée directement dans les locaux d’une organisation. Permet un contrôle total sur les données et la sécurité.
```



## Inventaire Ansible (Inventory)
```
Fichier listant les hôtes sur lesquels Ansible doit agir. Peut être en format INI, YAML ou dynamique. Définit les groupes, variables d’hôtes et environnements.
```



## Kernel Space
```
Zone de mémoire privilégiée où fonctionne le noyau de l’OS : gestion mémoire, processus, pilotes et interactions matérielles. Accès restreint pour garantir la stabilité.
```



## Machine virtuelle (VM)
```
Ordinateur logiciel simulé, fonctionnant à l’intérieur d’un hôte physique. Chaque VM possède son OS, ses applications et ses ressources virtuelles (CPU, RAM, disque).
```



## MicroVM
```
Machine virtuelle ultra-légère, conçue pour des charges rapides et isolées (ex. Firecracker). Combine la sécurité des VMs et la rapidité des conteneurs.
```



## Module Ansible
```
Composant exécuté sur les machines distantes pour effectuer une tâche précise : copier un fichier, installer un paquet, créer un utilisateur, gérer PostgreSQL, etc.
```



## OpenStack
```
Plateforme open source qui orchestre compute, réseau et stockage pour créer un cloud privé. Fonctionne via API, CLI et dashboard pour gérer un datacenter virtuel.
```



## Paravirtualisation
```
Technique où l’OS invité est modifié pour communiquer directement avec l’hyperviseur via des hypercalls, améliorant les performances mais exigeant un noyau adapté.
```



## Playbook Ansible
```
Fichier YAML décrivant les actions à exécuter sur une ou plusieurs machines : installation, configuration, déploiement, automatisation.
```



## Rings de privilège (Ring 0, Ring 3, Ring -1)
```
Système de niveaux de permissions du CPU.

Ring 0 : noyau

Ring 3 : applications

Ring –1 : hyperviseur
Ils garantissent isolation et sécurité du système.
```


## Rôle Ansible (Role)
```
Structure modulaire regroupant tâches, fichiers, handlers et variables. Facilite la réutilisation et l’organisation des configurations.
```



## Snapshot (virtualisation)
```
Capture instantanée de l’état d’une VM (disque, mémoire, configuration). Sert à revenir en arrière facilement lors de tests ou d’expérimentations.
```



## Souveraineté numérique
```
Capacité d’une organisation ou d’un État à contrôler ses données, infrastructures et technologies, sans dépendre de fournisseurs étrangers.
```



## SSH (Secure Shell)
```
SSH est un protocole sécurisé permettant de se connecter à distance à une machine, d’exécuter des commandes et de transférer des fichiers.
```



## Syscall (System Call)
```
Mécanisme qui permet à une application d’interagir avec le noyau : lire un fichier, créer un processus, envoyer des données réseau, etc.
```



## Task Ansible (Tâche)
```
Instruction décrivant une action unique à exécuter via un module. Une séquence de tasks forme un playbook ou un rôle.
```



## User Space
```
Espace mémoire où s’exécutent les applications. Cet espace a des privilèges limités pour éviter de compromettre le système.
```



## VBoxManage
```
Interface en ligne de commande de VirtualBox. Permet d’automatiser la création, le démarrage, la configuration et la suppression des VMs.
```



## VirtualBox
```
Hyperviseur Type 2 open source permettant de créer et gérer des VMs sur Windows, Linux ou macOS. Très utilisé pour la formation et le développement.
```



## Virtualisation
```
Technologie qui consiste à créer des environnements informatiques simulés (VM, réseaux, stockage) à partir d’un matériel physique unique. Elle permet d’exécuter plusieurs systèmes isolés sur la même machine.
```



## Virtualisation au niveau du système d’exploitation (OS-level / Containers)
```
Forme légère de virtualisation où plusieurs environnements isolés partagent le même noyau du système hôte. Exemples : Docker, LXC.
```



## Virtualisation complète (Full Virtualization)
```
Mode de virtualisation où le système invité ne sait pas qu’il est virtualisé. L’hyperviseur simule un matériel complet pour exécuter n’importe quel OS.
```



## Émulation
```
Simulation complète d’un matériel, souvent utilisé pour exécuter un OS conçu pour une autre architecture. Plus lente, car chaque instruction est traduite.
```



