# BAC+3-B01-M10-CMD

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS


## Modifier la politique d'exécution des scripts
```
Set-ExecutionPolicy <ModePolitique>
```

## Rechercher une commande PowerShell
```
Get-Command
```

## Rechercher les commandes d'un module avec wildcard
```
Get-Command *<MotCle>*
```

## Afficher l'aide d'une commande
```
Get-Help <Commande>
```

## Afficher le type, les propriétés et méthodes d'un objet
```
Get-Member
```

## Lister les processus
```
Get-Process
```

## Lister les services
```
Get-Service
```

## Lister le contenu d'un répertoire
```
Get-ChildItem
```

## Sélectionner des propriétés d'un objet
```
Select-Object
```

## Trier les données d'un objet
```
Sort-Object
```

## Compter ou mesurer des données d'un objet
```
Measure-Object
```

## Filtrer les objets selon une condition
```
Where-Object
```

## Sélectionner des propriétés précises
```
Get-ChildItem -File | Select Name,Length
```

## Créer une propriété calculée
```
Get-ChildItem -File | Select Name, @{ n='<NomAffiche>'; e={ $PSItem.<Propriete> }}
```

## Écrire le résultat d'une commande dans un fichier
```
<Commande> | Out-File
```

## Mettre en forme les données en tableau
```
Format-Table
```

## Mettre en forme les données en largeur
```
Format-Wide
```

## Mettre en forme les données en liste
```
Format-List
```

## Arrêter un service via le pipeline (By Value)
```
Get-Service <NomService> | Stop-Service
```

## Arrêter un service via InputObject
```
Get-Service <NomService> | Stop-Service -InputObject <NomService>
```

## Déclarer une variable contenant un objet
```
$<NomVariable> = Get-Service
```

## Appeler une propriété d'une variable
```
$<NomVariable>.name
```

## Appeler une méthode d'une variable
```
$<NomVariable>.Stop()
```

## Envoyer une variable au travers du pipeline
```
$<NomVariable> | Stop-Service
```

## Déclarer une variable à portée globale
```
$global:<NomVariable>
```

## Structure conditionnelle If / ElseIf / Else
```
If ($<Variable> -eq <Valeur1>) {
  <Traitement>
}
ElseIf ($<Variable> -eq <Valeur2>) {
  <Traitement>
}
Else {
  <Traitement>
}
```

## Structure de boucle While
```
While ($<Variable> -eq <Valeur>) {
  <Traitement>
}
```

## Structure de boucle Foreach
```
Foreach ($<Element> in $<Collection>) {
  <Traitement>
}
```

## Structure Switch
```
Switch ($<Variable>) {
  '<Valeur1>' { <Traitement> }
  '<Valeur2>' { <Traitement> }
  'Default' { <Traitement> }
}
```

## Capturer les erreurs d'une commande dans une variable
```
Get-ChildItem <CheminDossier> -ErrorVariable <NomVariableErreur>
```

## Afficher la dernière erreur générée
```
$Error[0]
```

## Activer le remoting PowerShell
```
Enable-PSRemoting
```

## Créer une session distante
```
$<NomSession> = New-PSSession -Computername <NomMachine>
```

## Déconnecter une session distante
```
Disconnect-PSSession -Session $<NomSession>
```

## Lister les sessions PowerShell
```
Get-PSSession
```

## Reconnecter une session distante
```
Get-PSSession -Computername <NomMachine> | Connect-PSSession
```

## Supprimer toutes les sessions PowerShell
```
Get-PSSession | Remove-PSSession
```

## Entrer dans une session distante interactive
```
$<NomSession> = Enter-PSSession -Computername <NomMachine>
```

## Lister les modules disponibles sur une session distante
```
Get-Module -PSSession $<NomSession> -ListAvailable
```

## Importer un module depuis une machine distante avec préfixe
```
Import-Module -PSSession $<NomSession> -name <NomModule> -Prefix <Prefixe>
```

## Envoyer une commande sur des machines distantes
```
Invoke-Command -Computername <Machine1>,<Machine2> -ScriptBlock { <Commande> }
```

## Passer une variable locale dans un Invoke-Command
```
Invoke-Command -Computername <Machine1>,<Machine2> -ScriptBlock { Get-Process $Using:<NomVariable> }
```

## Afficher le chemin des modules PowerShell
```
$env:PSModulePath
```