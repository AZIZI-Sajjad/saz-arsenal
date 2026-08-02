# BAC+3-B01-M09-CMD

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS


## Exécuter un script Bash en chemin relatif
```
./<NomScript>.sh
```

## Rendre un script exécutable
```
chmod a+x <NomScript>.sh
```

## Shebang à placer en première ligne d'un script
```
#!/bin/bash
```

## Assigner la sortie d'une commande à une variable (syntaxe {})
```
<NomVariable>=${<Commande>}
```

## Assigner la sortie d'une commande à une variable (backquotes)
```
<NomVariable>=`<Commande>`
```

## Syntaxe d'un test entre crochets
```
[ <ConditionATester> ]
```

## Tester l'existence d'un fichier
```
[ -e <CheminFichier> ]
```

## Tester si une chaîne est vide
```
[ -z $<NomVariable> ]
```

## Tester si une chaîne n'est pas vide
```
[ -n $<NomVariable> ]
```

## Tester l'égalité de deux chaînes
```
[ $<Variable1> = $<Variable2> ]
```

## Tester la différence de deux chaînes
```
[ $<Variable1> != $<Variable2> ]
```

## Structure conditionnelle if / elif / else
```
if [ <Condition1> ]
then
  <Commande>
elif [ <Condition2> ]
then
  <Commande>
else
  <Commande>
fi
```

## Structure de boucle for
```
for <Variable> in <Objet1> <Objet2> <ObjetN>
do
  <Commande>
done
```

## Passer des arguments à un script
```
./<NomScript>.sh <Argument1> <Argument2> <Argument3> <Argument4>
```

## Décaler les arguments de position
```
shift
```

## Afficher le code retour de la dernière commande
```
echo $?
```

## Structure de boucle while
```
while [ <Condition> ]
do
  <Commande>
done
```

## Chaîner deux commandes en cas de succès (AND)
```
apt update && apt install <Paquet>
```

## Chaîner deux commandes en cas d'échec (OR)
```
ls -l <NomFichier> || echo "Le fichier n'existe pas"
```

## Déclarer une fonction avec arguments
```
function <NomFonction>() {
  echo "$1 est le premier argument"
  echo "$2 est le deuxième argument"
}

<NomFonction> <Argument1> <Argument2>
```

## Supprimer un fichier récursivement avec wildcard
```
rm -Rf *
```

## Écrire un message de log
```
logger "<Message>"
```

## Écrire un log avec un tag
```
logger -t <Tag> "<Message>"
```

## Écrire un log avec tag et numéro de processus
```
logger -i -t <Tag> "<Message>"
```

## Déclarer un tableau bash
```
<NomTableau>=(<Valeur0> <Valeur1> <Valeur2> <Valeur3>)
```

## Accéder à une valeur d'un tableau par indice
```
echo ${<NomTableau>[<Indice>]}
```

## Afficher tous les éléments d'un tableau
```
echo ${<NomTableau>[*]}
```

## Lire une entrée dans un tableau
```
read -a <NomTableau>
```

## Supprimer une variable
```
unset <NomVariable>
```

## Exporter une variable aux processus fils
```
export <NomVariable>
```

## Découper une chaîne en variables de position avec set et IFS
```
CHAINE="<ChaineAvecDelimiteurs>"
IFS=<Delimiteur>
set $CHAINE
echo $2
```

## Supprimer une ligne d'un fichier avec sed
```
sed '<NumeroLigne> d' <NomFichier>
```

## Supprimer plusieurs lignes avec sed
```
sed '<Ligne1> d; <Ligne2> d' <NomFichier>
```

## Supprimer une plage de lignes avec sed
```
sed '<LigneDebut>,<LigneFin> d' <NomFichier>
```

## Substituer la première occurrence avec sed
```
sed 's/<ElementASubstituer>/<Substituant>/' <NomFichier>
```

## Substituer toutes les occurrences avec sed
```
sed 's/<ElementASubstituer>/<Substituant>/g' <NomFichier>
```

## Translitérer des caractères avec sed
```
sed 'y/<ListeATransliterer>/<ListeDeTransliteration>/' <NomFichier>
```

## Rediriger les erreurs vers /dev/null
```
2> /dev/null
```