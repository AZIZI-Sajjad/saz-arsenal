# saz-git

#plateform/git
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/git



## Git - commit sur une branche déjà existante
```
git branch
git switch debug-branche
git status
git add .
git commit -m "Modification debug"
git push
```

## Git - premier push d’une branche
```
git push -u origin debug-branche
```

## Git - créer une branche et commit dessus
```
git switch -c debug-branche
git status
git add .
git commit -m "Create debug branche"
git push -u origin debug-branche
```

## Git - vérifier la branche distante liée
```
git branch -vv
```

## Git - corriger l’erreur upstream
```
git push --set-upstream origin debug-branche
```

## Git - workflow après le premier push
```
git status
git add .
git commit -m "Autre modification"
git push
```