# saz-aws

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/terraform


# Terraform - Configurer les accès AWS
```
aws configure
```

# Terraform - Lister la configuration active
```
aws configure list
```

# Terraform - Valider les clés d'accès
```
aws sts get-caller-identity
```

# Terraform - Extraire l'ARN utilisateur
```
aws sts get-caller-identity --query "Arn"
```

# Terraform - Extraire l'ID du compte
```
aws sts get-caller-identity --query "Account"
```

# Terraform - Lister les détails EC2
```
aws ec2 describe-instances
```

# Terraform - Extraire les IDs EC2
```
aws ec2 describe-instances --query "Reservations[*].Instances[*].InstanceId" --output text
```

# Terraform - Extraire les IDs EC2 (Paris)
```
aws ec2 describe-instances --region eu-west-3 --query "Reservations[*].Instances[*].InstanceId" --output text
```
