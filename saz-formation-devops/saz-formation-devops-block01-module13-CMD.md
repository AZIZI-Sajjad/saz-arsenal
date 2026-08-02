# BAC+3-B01-M13-CMD

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS


## Ressource Terraform - instance AWS EC2 avec output
```
resource "aws_instance" "<NomRessource>" {
  ami           = "<AmiId>"
  instance_type = "<TypeInstance>"
}

output "id" {
  value = aws_instance.<NomRessource>.id
}
```

## Initialiser le répertoire de travail Terraform
```
terraform init
```

## Visualiser le plan d'exécution
```
terraform plan
```

## Appliquer le plan et créer/modifier l'infrastructure
```
terraform apply
```

## Formater les fichiers de configuration Terraform
```
terraform fmt
```

## Détruire l'infrastructure managée
```
terraform destroy
```

## Ressource Terraform - VPC AWS avec tags
```
resource "aws_vpc" "<NomVpc>" {
  cidr_block = "<CidrBlock>"
  tags = {
    Name        = "<NomTag>"
    Environment = "<Environnement>"
  }
}
```

## Ressource Terraform - subnet dans un VPC
```
resource "aws_subnet" "<NomSubnet>" {
  cidr_block              = "<CidrBlock>"
  vpc_id                  = aws_vpc.<NomVpc>.id
  availability_zone       = "<AvailabilityZone>"
  map_public_ip_on_launch = false
  tags = {
    Name        = "<NomTag>"
    Environment = "<Environnement>"
  }
}
```

## Ressource Terraform - security group dans un VPC
```
resource "aws_security_group" "<NomSg>" {
  name_prefix = "<PrefixeNom>"
  vpc_id      = aws_vpc.<NomVpc>.id
  tags = {
    Environment = "<Environnement>"
    Type        = "<TypeSg>"
  }
}
```

## Ressource Terraform - règle de security group
```
resource "aws_security_group_rule" "<NomRegle>" {
  security_group_id = aws_security_group.<NomSg>.id
  type              = "ingress"
  from_port         = "<PortDebut>"
  to_port           = "<PortFin>"
  protocol          = "tcp"
  cidr_blocks       = ["<CidrAutorise>"]
}
```

## Ressource Terraform - instance EC2 avec subnet et SG
```
resource "aws_instance" "<NomInstance>" {
  ami                    = "<AmiId>"
  instance_type          = "<TypeInstance>"
  subnet_id              = aws_subnet.<NomSubnet>.id
  vpc_security_group_ids = [aws_security_group.<NomSg>.id]
  tags = {
    Name = "<NomTag>"
    Role = "<Role>"
  }
}
```

## Datasource Terraform - récupérer une EIP par IP publique
```
data "aws_eip" "<NomDatasource>" {
  public_ip = "<IpPublique>"
}
```

## Datasource Terraform - récupérer la région courante
```
data "aws_region" "current" {}
```

## Déclarer une variable Terraform
```
variable "<NomVariable>" {
  type        = <Type>
  default     = <ValeurParDefaut>
  description = "<Description>"
}
```

## Déclarer une variable de type map
```
variable "<NomVariable>" {
  type    = map(string)
  default = {}
}
```

## Déclarer une variable de type liste d'objets
```
variable "<NomVariable>" {
  description = "<Description>"
  type = list(object({
    dns_record_name = string
    dns_record_type = string
    dns_record_ttl  = number
    dns_record_ips  = list(string)
  }))
}
```

## Passer une variable en ligne de commande
```
terraform apply -var '<NomVariable>=<Valeur>'
```

## Passer un fichier de variables
```
terraform apply -var-file <CheminFichier>.tfvars
```

## Déclarer un bloc locals
```
locals {
  <NomLocal> = "${var.<NomVariable>}-<Suffixe>"
}
```

## Afficher la valeur d'un output depuis le tfstate
```
terraform output
```

## Meta-parameter depends_on - forcer une dépendance
```
resource "aws_instance" "<NomInstance>" {
  ami           = "<AmiId>"
  instance_type = "<TypeInstance>"
  depends_on    = ["aws_instance.<Dependance>"]
}
```

## Meta-parameter lifecycle - ignorer des changements
```
resource "aws_instance" "<NomInstance>" {
  ami           = "<AmiId>"
  instance_type = "<TypeInstance>"
  lifecycle {
    ignore_changes = ["ami"]
  }
}
```

## Meta-parameter count - boucler sur la création
```
resource "aws_instance" "<NomInstance>" {
  ami           = "<AmiId>"
  instance_type = "<TypeInstance>"
  count         = <NombreOccurrences>
  tags = {
    Name = "<Nom>-${count.index}"
  }
}
```

## Meta-parameter for_each - boucler sur un set
```
resource "aws_instance" "<NomInstance>" {
  for_each      = toset(["<Val1>", "<Val2>", "<Val3>"])
  ami           = "<AmiId>"
  instance_type = "<TypeInstance>"
  tags = {
    Name = "<Nom>-${each.key}"
  }
}
```

## Expression conditionnelle - ternaire dans count
```
resource "aws_instance" "<NomInstance>" {
  count         = var.<NomVariable> ? 1 : 0
  ami           = "<AmiId>"
  instance_type = "<TypeInstance>"
}
```

## Expression for loop - transformer une liste
```
cidr_blocks = [for i in var.<NomVariable> : "${i}/32"]
```

## Bloc dynamique - générer des blocs de configuration
```
dynamic "ingress" {
  for_each = var.<NomVariable>
  content {
    from_port = ingress.value
    to_port   = ingress.value
    protocol  = "tcp"
  }
}
```

## Validation personnalisée d'une variable
```
variable "<NomVariable>" {
  type        = string
  description = "<Description>"
  validation {
    condition     = substr(var.<NomVariable>, 0, 4) == "<Prefixe>"
    error_message = "<MessageErreur>"
  }
}
```

## Générer un fichier via templatefile
```
data "template_file" "<NomDatasource>" {
  template = file("<CheminTemplate>.tpl")
  vars = {
    <NomVar> = <Valeur>
  }
}
```

## Générer la documentation d'un module en table Markdown
```
terraform-docs markdown table .
```

## Créer un nouveau workspace
```
terraform workspace new <NomWorkspace>
```

## Lister les workspaces
```
terraform workspace list
```

## Sélectionner un workspace
```
terraform workspace select <NomWorkspace>
```

## Appeler un module
```
module "<NomModule>" {
  source = "<SourceModule>"
  <Arg1> = "<Valeur1>"
  <Arg2> = "<Valeur2>"
}
```

## Exécuter apply sur plusieurs modules avec Terragrunt
```
terragrunt apply-all
```

## Exécuter destroy sur plusieurs modules avec Terragrunt
```
terragrunt destroy-all
```

## Exécuter plan sur plusieurs modules avec Terragrunt
```
terragrunt plan-all
```

## Exécuter output sur plusieurs modules avec Terragrunt
```
terragrunt output-all
```

## Configurer un backend S3 avec verrou
```
terraform {
  backend "s3" {
    use_lockfile = "true"
    bucket       = "<NomBucket>"
    key          = "<CheminTfstate>"
  }
}
```

## Fixer la version de Terraform et des providers
```
terraform {
  required_version = "<VersionTerraform>"
  required_providers {
    aws      = ">= <VersionAws>"
    template = "= <VersionTemplate>"
    gitlab   = "~> <VersionGitlab>"
  }
}
```

## Débloquer un lock d'état bloqué
```
terraform force-unlock <LockId>
```

## Lister les ressources du tfstate
```
terraform state list
```

## Afficher le contenu d'un item du tfstate
```
terraform state show <CheminRessource>
```

## Importer une ressource existante dans le tfstate
```
terraform import <TypeRessource>.<NomRessource> <IdRessource>
```

## Activer le mode debug Terraform
```
export TF_LOG=DEBUG
```

## Valider la configuration Terraform
```
terraform validate
```

## Exécuter les tests Terraform
```
terraform test
```