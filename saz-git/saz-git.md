# saz-git

#plateform/git
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/git

# saz-git

## Git - Initialiser un nouveau repo
```bash
git init
```

## Git - Configurer le nom utilisateur
```bash
git config user.name "<User_Name>"
```

## Git - Configurer l'email
```bash
git config user.email "<adresse_Mail>"
```

## Git - Cloner un repo via SSH
```bash
git clone <ssh_link_to_repo>
```

## Git - Cloner un repo via HTTPS
```bash
git clone <https_link_to_repo>
```

## Git - Vérifier le status du repo
```bash
git status
```

## Git - Voir les fichiers trackés
```bash
git ls-files
```

## Git - Ajouter tous les fichiers au staging
```bash
git add .
```

## Git - Ajouter un fichier spécifique au staging
```bash
git add <file_Name_or_path_to_file>
```

## Git - Ajouter un dossier au staging
```bash
git add <dossier>
```

## Git - Retirer tous les fichiers du staging
```bash
git reset
```

## Git - Retirer un fichier du staging
```bash
git reset <file_Name_or_path_to_file>
```

## Git - Retirer le dernier commit du staging
```bash
git reset HEAD~1
```

## Git - Commiter les changements
```bash
git commit -m "<Message_du_commit>"
```

## Git - Modifier et commiter d'un coup
```bash
git commit -am "<Message_du_commit>"
```

## Git - Voir l'historique des commits
```bash
git log
```

## Git - Voir l'historique en une ligne
```bash
git log --oneline
```

## Git - Voir l'historique avec un graphique
```bash
git log --graph --all --decorate
```

## Git - Voir l'historique avec les diffs
```bash
git log --all -p
```

## Git - Voir les changements non commités
```bash
git diff
```

## Git - Voir les changements d'un fichier spécifique
```bash
git diff <file_Name_or_path_to_file>
```

## Git - Voir les changements en staging
```bash
git diff --staged
```

## Git - Voir la différence entre deux commits
```bash
git diff <commit1> <commit2>
```

## Git - Voir la différence entre HEAD et le commit précédent
```bash
git diff HEAD~1 HEAD
```

## Git - Afficher un commit spécifique
```bash
git show commit-hash
```

## Git - Afficher le dernier commit
```bash
git show HEAD
```

## Git - Créer une nouvelle branche
```bash
git branch <branch_Name>
```

## Git - Créer et basculer vers une nouvelle branche
```bash
git switch -c <branch_Name>
```

## Git - Créer et basculer via checkout
```bash
git checkout -b <branch_Name>
```

## Git - Lister les branches locales
```bash
git branch
```

## Git - Lister toutes les branches
```bash
git branch -a
```

## Git - Lister les branches avec le tracking
```bash
git branch -vv
```

## Git - Basculer vers une branche
```bash
git switch <branch_Name>
```

## Git - Basculer via checkout
```bash
git checkout <branch_Name>
```

## Git - Supprimer une branche
```bash
git branch -d <branch_Name>
```

## Git - Forcer la suppression d'une branche
```bash
git branch -D <branch_Name>
```

## Git - Vérifier la branche courante
```bash
git branch
```

## Git - Voir le status avant de commiter
```bash
git status
```

## Git - Commiter sur la branche courante
```bash
git commit -m "<Commit_Message>"
```

## Git - Pousser les changements
```bash
git push
```

## Git - Pousser une branche pour la première fois
```bash
git push -u origin <branch_Name>
```

## Git - Créer une branche et commiter
```bash
git switch -c <branch_Name>
```

## Git - Ajouter tous les changements
```bash
git add .
```

## Git - Créer un commit
```bash
git commit -m "<Commit_Message>"
```

## Git - Pousser la nouvelle branche
```bash
git push -u origin <branch_Name>
```

## Git - Corriger l'erreur upstream
```bash
git push --set-upstream origin <branch_Name>
```

## Git - Pousser les changements après le premier push
```bash
git push
```

## Git - Fusionner une branche
```bash
git merge <branch_Name>
```

## Git - Rebase une branche
```bash
git rebase main
```

## Git - Basculer vers main avant le rebase
```bash
git switch main
```

## Git - Fusionner après un rebase
```bash
git merge <branch_Name>
```

## Git - Annuler le dernier commit (soft)
```bash
git reset --soft HEAD~1
```

## Git - Annuler le dernier commit (mixed)
```bash
git reset --mixed HEAD~1
```

## Git - Annuler le dernier commit (hard)
```bash
git reset --hard HEAD~1
```

## Git - Modifier le message du dernier commit
```bash
git commit --amend -m "<Commit_Message>"
```

## Git - Récupérer les changements du remote
```bash
git fetch
```

## Git - Récupérer depuis un remote spécifique
```bash
git fetch origin
```

## Git - Récupérer et fusionner
```bash
git pull
```

## Git - Récupérer et fusionner depuis main
```bash
git pull origin main
```

## Git - Pousser vers main
```bash
git push origin main
```

## Git - Pousser une branche spécifique
```bash
git push origin <branch_Name>
```

## Git - Pousser en force
```bash
git push --force
```

## Git - Pousser en force avec sécurité
```bash
git push --force-with-lease origin main
```

## Git - Mettre en stash les changements
```bash
git stash
```

## Git - Mettre en stash avec une description
```bash
git stash save "<Description_du_stash>"
```

## Git - Voir la liste des stash
```bash
git stash list
```

## Git - Appliquer et supprimer un stash
```bash
git stash pop
```

## Git - Appliquer un stash spécifique
```bash
git stash apply stash@{0}
```

## Git - Supprimer un stash
```bash
git stash drop stash@{0}
```

## Git - Chercher un commit avec un keyword
```bash
git log --grep="keyword"
```

## Git - Chercher dans l'historique avec grep
```bash
git log --oneline | grep "keyword"
```

## Git - Trouver qui a modifié une ligne
```bash
git blame <file_Name_or_path_to_file>
```

## Git - Trouver qui a modifié une plage de lignes
```bash
git blame -L 10,20 <file_Name_or_path_to_file>
```

## Git - Voir les branches fusionnées
```bash
git branch --merged
```

## Git - Voir les branches non fusionnées
```bash
git branch --no-merged
```

## Git - Renommer la branche courante
```bash
git branch -m <new_Name>
```

## Git - Renommer une branche spécifique
```bash
git branch -m ancien-nom <new_Name>
```

## Git - Nettoyer les branches supprimées du remote
```bash
git fetch --prune
```

## Git - Nettoyer avec prune
```bash
git remote prune origin
```

## Git - Ajouter un remote
```bash
git remote add origin <ssh_link_to_repo>
```

## Git - Ajouter un remote upstream
```bash
git remote add upstream https://github.com/autre/repo.git
```

## Git - Voir les remotes
```bash
git remote
```

## Git - Voir les remotes avec les URLs
```bash
git remote -v
```

## Git - Changer l'URL d'un remote
```bash
git remote set-url origin git@github.com:nouvel-utilisateur/repo.git
```

## Git - Supprimer un remote
```bash
git remote remove origin
```

## Git - Ajouter des règles au gitignore
```bash
cat >> .gitignore << 'EOF'
*.log
node_modules/
.env
EOF
```

## Git - Vérifier ce que Git ignore
```bash
git check-ignore -v <file_Name_or_path_to_file>
```

## Git - Vérifier les fichiers ignorés dans un dossier
```bash
git check-ignore -v terraform/*
```

## Git - Voir les fichiers non trackés
```bash
git status --porcelain
```

## Git - Voir les fichiers non trackés en détail
```bash
git ls-files --others --exclude-standard
```

## Git - Forcer le tracking d'un fichier ignoré
```bash
git add -f fichier.log
```

## Git - Supprimer un fichier du repo sans le supprimer localement
```bash
git rm --cached <file_Name_or_path_to_file>
```

## Git - Ajouter les fichiers supprimés
```bash
git add -u
```

## Git - Voir les changements par auteur
```bash
git log --author="<User_Name>"
```

## Git - Voir le résumé des commits par auteur
```bash
git shortlog -sn
```

## Git - Configurer le nom globalement
```bash
git config --global user.name "<User_Name>"
```

## Git - Configurer l'email globalement
```bash
git config --global user.email "<adresse_Mail>"
```

## Git - Voir la configuration
```bash
git config --list
```

## Git - Installation de git-filter-repo
```bash
pip3 install --user git-filter-repo
```

## Git - Ajouter git-filter-repo au PATH
```bash
export PATH="$HOME/.local/bin:$PATH"
```

## Git - Vérifier la version de git-filter-repo
```bash
git filter-repo --version
```

## Git - Purger des fichiers spécifiques
```bash
git filter-repo --force \
  --path peojets/basic/aws.tfvars \
  --path peojets/adv-1/aws.tfvars \
  --path peojets/adv-2/aws.tfvars \
  --path peojets/adv-3/aws.tfvars \
  --path peojets/adv-4/aws.tfvars \
  --path peojets/adv-301/aws.tfvars \
  --invert-paths
```

## Git - Purger tous les fichiers .tfvars
```bash
git filter-repo --force --filename-pattern '*.tfvars' --invert-paths
```

## Git - Chercher les secrets AKIA
```bash
git log --all -p --diff-filter=A -- '*.tfvars' | grep -B 5 "AKIA\|access_key"
```

## Git - Vérifier que l'historique est clean
```bash
git log --all -p | grep -i "AKIA\|access_key\|secret_key" || echo "Clean"
```

## Git - Lister tous les fichiers .tfvars dans l'historique
```bash
git log --all --diff-filter=A --name-only --pretty=format: -- '*.tfvars' | sort -u
```

## Git - Rajouter le remote après filter-repo
```bash
git remote add origin git@github.com:utilisateur/visiplus-terraform-projets-perso.git
```

## Git - Pousser en force après filter-repo
```bash
git push --force origin main
```

## Git - Copier aws.tfvars en aws.tfvars.example
```bash
for dir in projets/adv-1 projets/adv-2 projets/adv-3 projets/adv-4 projets/basic; do
  cp "$dir/aws.tfvars" "$dir/aws.tfvars.example"
  sed -i 's/=.*/="CHANGE_ME"/' "$dir/aws.tfvars.example"
done
```

## Git - Copier terraform.tfvars en example
```bash
cp projets/adv-2/terraform.tfvars projets/adv-2/terraform.tfvars.example
sed -i 's/=.*/="CHANGE_ME"/' projets/adv-2/terraform.tfvars.example
```

## Git - Ajouter les règles .gitignore pour Terraform
```bash
cat >> .gitignore << 'EOF'
*.tfvars
*.tfstate
*.tfstate.*
.terraform/
EOF
```

## Git - commit sur une branche déjà existante
```
git branch
git switch <branch_Name>
git status
git add .
git commit -m "<Commit_Message>"
git push
```

## Git - premier push d’une branche
```
git push -u origin <branch_Name>
```

## Git - créer une branche et commit dessus
```
git switch -c <branch_Name>
git status
git add .
git commit -m "<Commit_Message>"
git push -u origin <branch_Name>
```

## Git - vérifier la branche distante liée
```
git branch -vv
```

## Git - corriger l’erreur upstream
```
git push --set-upstream origin <branch_Name>
```

## Git - workflow après le premier push
```
git status
git add .
git commit -m "Autre modification"
git push
```