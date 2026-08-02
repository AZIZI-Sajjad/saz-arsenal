# BAC+3-B01-M03-CMD

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS


## Construire une image Docker à partir du Dockerfile
```
docker build
```

## Lancer un conteneur à partir de l'image
```
docker run
```

## Inventaire Ansible des serveurs par environnement
```
[dev]
<IP> ansible_user=<NomUtilisateur> ansible_ssh_private_key_file=<CheminClePrivee>

[recette]
<IP> ansible_user=<NomUtilisateur> ansible_ssh_private_key_file=<CheminClePrivee>
```

## Playbook Ansible de provisioning Docker sur une VM
```
---
- name: Provision VM pour Petclinic
  hosts: "{{ target_env }}"
  become: yes
  tasks:
  - name: Installer Docker
    apt:
      name: docker.io
      state: present
      update_cache: yes
  - name: Activer et démarrer le service Docker
    systemd:
      name: docker
      enabled: yes
      state: started
```

## Terraform - définir le provider DigitalOcean (main.tf)
```
provider "digitalocean" {
  token = var.do_token
}
```

## Terraform - déclarer une variable sensible (variables.tf)
```
variable "do_token" {
  description = "DO API Token"
  type = string
  sensitive = true
}
```

## Terraform - fournir la valeur de la variable (terraform.tfvars)
```
do_token = "<TokenAPI>"
```

## Terraform - déclarer un cluster Kubernetes
```
resource "digitalocean_kubernetes_cluster" "my_cluster" {
  name = "<NomCluster>"
  region = "<Region>"
  version = "<VersionKubernetes>"
  node_pool {
    name = "<NomNodePool>"
    size = "<TailleNode>"
    node_count = <NombreNodes>
  }
}
```

## Terraform - initialiser le répertoire de travail
```
terraform init
```

## Terraform - afficher les changements à appliquer
```
terraform plan
```

## Terraform - appliquer les changements
```
terraform apply
```