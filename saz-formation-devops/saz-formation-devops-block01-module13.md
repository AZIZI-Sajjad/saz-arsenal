# BAC+3-B01-M13-FC

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS


## Terraform Registry
```
Catalogue public (ou privé) contenant des modules et providers prêts à l’emploi. Permet de réutiliser du code IaC standardisé, vérifié et versionné.
```

## Terraform apply
```
Commande appliquant réellement les changements définis dans la configuration.
```

## Infrastructure as Code (IaC)
```
Méthode qui consiste à gérer, provisionner et configurer une infrastructure informatique via du code plutôt qu’avec des actions manuelles.
```

## Resource Terraform
```
Bloc HCL décrivant un objet réel à créer (ex : instance EC2, bucket S3, VPC) que doit créer Terraform.
```

## Approche déclarative
```
Style IaC où l’on décrit l’état final souhaité, et l’outil (ex : Terraform) décide des étapes nécessaires pour y parvenir.
```

## Terraform destroy
```
Commande supprimant toutes les ressources gérées par Terraform.
```

## Lock Terraform
```
Mécanisme empêchant deux opérations concurrentes d’écrire en même temps sur le tfstate.
```

## Hashicorp Configuration Language (HCL)
```
Langage de configuration utilisé par Terraform. Déclaratif, lisible, typé, compatible JSON, conçu pour décrire des infrastructures de manière simple et modulaire.
```

## Workspace Terraform
```
Système permettant d’utiliser le même code avec des états différents (environnements multiples).
```

## Virtual Private Cloud (VPC)
```
Réseau virtuel isolé dans AWS où sont déployées les ressources (subnets, route tables, gateways…).
```

## Variable et Local Terraform
```
La varibale est un paramètre d’entrée qui rend la configuration flexible et réutilisable alors que la local est une valeur interne calculée dans le code Terraform, non surchargeable par un tfvars.
```

## Terraform init
```
Commande initialisant un projet Terraform et téléchargeant les providers.
```

## Module Terraform
```
Ensemble de fichiers Terraform réutilisables permettant de factoriser et structurer le code.
```

## Graph de dépendances Terraform
```
Structure utilisée par Terraform pour déterminer l’ordre d’exécution des ressources. Terraform construit un graphe orienté acyclique (DAG) pour orchestrer la création, mise à jour ou destruction.
```

## Autoscaling
```
Mécanisme cloud qui ajuste automatiquement le nombre de ressources (instances, pods, lambdas) selon la charge : augmentation en pic, réduction en basse activité.
```

## Serverless
```
Modèle cloud où l’utilisateur ne gère ni serveurs, ni infrastructure : l’exécution est entièrement automatisée (ex : AWS Lambda). La facturation est à l’usage et la scalabilité automatique.
```

## Terraform plan
```
Commande affichant les actions prévues, sans modifier l’infrastructure(Dry Run).
```

## Backend Terraform
```
Système de stockage du tfstate (ex : S3, GCS, local).
```

## Stateful vs Stateless
```
Stateful : Un système qui conserve l’état entre deux exécutions (ex : une base de données qui mémorise les sessions).
```

## Immutable Infrastructure
```
Principe où chaque changement implique de recréer des ressources plutôt que les modifier sur place à l'opposé de mutable où l’on applique des modifications directement sur les ressources existantes.
```

## Datasource Terraform
```
Bloc permettant de lire des informations existantes sans créer de ressource (ex : récupérer une AMI).
```

## Lifecycle Terraform
```
Bloc permettant de modifier le comportement de création/destruction d’une ressource (create_before_destroy, prevent_destroy, etc.)
```

## Region AWS
```
Zone géographique contenant plusieurs zones de disponibilité (AZ) pour déployer des ressources.
```

## Cloud-Native
```
Approche de conception d’applications optimisées pour le cloud : services distribués, conteneurs, microservices, DevOps, scalabilité dynamique.
```

## Provider Terraform
```
Plugin qui permet à Terraform d’interagir avec une plateforme (ex : AWS, GCP, Azure).
```

## Output Terraform
```
Valeur exposée après exécution (ex : ID d’instance), stockée dans le tfstate.
```

## Terraform State (tfstate)
```
Fichier contenant l’état réel de l’infrastructure déployée pour permettre la comparaison avec le code.
```

## Rolling Update
```
Méthode de déploiement qui remplace les instances ou services une par une, sans interruption globale, en garantissant une disponibilité continue.
```

## Availability Zone (AZ)
```
Centre(s) de données isolés au sein d’une région, assurant redondance et haute disponibilité.
```

## Approche impérative
```
Style IaC où l'on décrit étape par étape comment atteindre le résultat final. (ex: Ansible)
```