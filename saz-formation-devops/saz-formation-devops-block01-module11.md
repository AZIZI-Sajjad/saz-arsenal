# BAC+3-B01-M11-FC

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS

## Spring Data
```
Regroupe de modules Spring pour la gestion des interactions avec des bases de données	.
```

## Spring Security
```
Module de Spring pour gérer les problématiques de sécurité. Il permet par exemple de mettre en place l'authentification par session ou jeton et l'autorisation par rôles ou autorités.
```

## Contrôle d'accès
```
En développement logiciel, un contrôle d'accès est un point de l'architecture logicielle permettant de vérifier l'identité du demandeur et ses autorisations associées à la demande.
```

## SSRF
```
SSRF, qui signifie Server-side Request Forgery, est une attaque dont le but est d'amener un code côté serveur à exécuter une requête indésirable, profitant ainsi des autorisations accordées au code en question.
```

## Spring Web
```
Module de Spring permettant le développement d'application web grâce à la gestion des requêtes HTTP.
```

## XSS
```
XSS, qui signifie Cross-site Scripting, est une attaque qui consiste à introduire un script malveillant sur la page d'une application web. Ce script  impactera le comportement du navigateur de l'utilisateur.
```

## Architecture logicielle
```
Une architecture logicielle se définit par les sous ensembles nommés composants logiciels qui la composent et les interactions entre ces sous ensembles.
```

## Autorisation
```
Vérification des droits accordés à un utilisateur authentifié, généralement via l'attribution de rôles.
```

## Authentification
```
Vérification de l'identité d'un utilisateur, généralement via un nom d'utilisateur et un mot de passe.
```

## API
```
Une API est un logiciel permettant à d'autres logiciels de le solliciter via de requêtes. En retour, l'API fournira une réponse. Les API web utilisent le protocole HTTP. Une API est généralement considérée comme étant un backend au sein d'une architecture logicielle.
```

## Jeton
```
Dans le contexte des applications web un jeton est un mécanisme sans état où le client conserve ce jeton et l'envoie à chaque requête au serveur pour que ce dernier exécute le processus d'autorisation. Le serveur ne conserve pas le jeton.
```

## Spring Boot
```
Module de Spring permettant la création d'une application JAVA opérationnelle permettant l'auto configuration des autres modules Spring utilisé, l'ajout des dépendances via des starters de dépendances, un développement et un déploiement facilité.
```

## Cryptographie
```
Ensemble des procédés visant à crypter des informations pour en assurer la confidentialité entre l'émetteur et le destinataire.
```

## Spring
```
Framework JAVA permettant la création d'application JAVA et traitement de nombreuses problématiques : l'interaction avec les bases de données, la sécurisation de l'application, sa configuration, le traitement de requêtes http, etc.
```

## Session
```
Dans le contexte des applications web une session est un mécanisme à état où tant le client que le serveur maintienne des informations sur l'utilisateur qui utilise l'application web pour assurer les processus d'authentification et d'autorisation.
```

## TypeScript
```
Langage de programmation basé sur JavaScript imposant plus de rigueur et de cadre.
```

## Angular
```
Framework TypeScript permettant de le développement d'application web performante et réactive.
```

## OWASP
```
La fondation OWASP s'efforce d'améliorer la sécurité des logiciels par le biais de projets de logiciels libres dirigés par la communauté, de centaines de chapitres, de dizaines de milliers de membres, et en organisant des conférences locales et mondiales.
```

## CSRF
```
CSRF qui signifie Cross Site Request Forgery fait référence à une attaque exploitant une vulnérabilité sur une application web. L'utilisateur cible de cette attaque va exécuter à son insu un traitement indésirables sur l'application web ciblée.
```

## Java
```
Langage de programmation reposant sur le paradigme Objet. Il a aussi pour caractéristique d'être fortement typé, compilé et repose sur l'utilisation d'une JVM (Java Virtual Machine) pour l'exécution.
```

## TOP 10 Vulnérabilités des APP WEB
```
- A01 : contrôles d'accès défaillants
- A02 : défaillances cryptographiques
- A03 : injection
- A04 : conception non sécurisée
- A05 : mauvaise configuration de sécurité
- A06 : composants vulnérables et obsolètes
- A07 : identification et authentification de mauvaise qualité
- A08 : manque d'intégrité des données et du logiciel
- A09 : carence des systèmes de contrôle et de journalisation
- A10 : falsification de requêtes côté serveur
```

## 10 Recommandation de OWASP Pour Sécuriser des applications (Web)
```
Recommandation A01-2021 : Broken Access Control
Recommandation A02-2021 : cryptographic failure
Recommandation A03-2021 : injection
Recommandation A04-2021 : insecure design
Recommandation A05-2021 : security misconfiguration
Recommandation A06-2021 : Vulnerable and Outdated Components
Recommandation A07-2021 : Identification and Authentication Failures
Recommandation A08-2021 : Software and Data Integrity Failures
Recommandation A09-2021 : Security Logging and Monitoring Failures
Recommandation A10-2021 : Server-Side Request Forgery (SSRF)
```


## OAuth2 Vs OpenID
```
OAuth 2.0 : sert à donner des autorisations à une application.

Exemple : autoriser une application à accéder à ton Google Drive.

OpenID Connect (OIDC) : sert à identifier et connecter un utilisateur. Il repose sur OAuth 2.0.

Exemple :

Accéder à Google Drive → OAuth 2.0
« Se connecter avec Google » → OpenID Connect

Résumé :

OAuth 2.0 = Que peux-tu faire ?
OpenID Connect = Qui es-tu ?
```

## C01 - Introduction à la sécurité des applications web :
```
-->  Introduction


-->  Contexte

- Démocratisation des applications web
  - Dans de nombreux domaines métiers
  - Avec de nombreuses technologies différentes
  - Par de nombreux développeurs

-->  Problématique

- Les applications web sont devenues des cibles privilégiées pour des attaques malveillantes
- Comment affronter ces menaces ?

-->  Critères de sécurité

- Vérifier les applications web en examinant quatre critères
  - Confidentialité
  - Disponibilité
  - Intégrité
  - Traçabilité

-->  Confidentialité

- Être en mesure de garantir que seules les personnes autorisées accèdent aux données qui correspondent à leurs droits
- Exemple : un client d'une banque ne doit pas accéder au compte d'un autre client

-->  Disponibilité

- Garantir que l'application est toujours disponible au moment où elle est censée être sollicitée
- Exemple : un site d'e-commerce devrait être constamment accessible indépendamment du moment ou de la quantité d'utilisateurs simultanés

-->  Intégrité

- Garantir qu'une donnée ne soit pas altérée, que ce soit en la rendant incomplète ou erronée
- Exemple : une donnée client ne doit pas pouvoir être modifiée à l'insu du client

-->  Traçabilité

- Garantir que les traitements effectués soient tracés en identifiant l'origine, le moment et l'action réalisée
- Exemple : chaque opération réalisée est enregistrée dans une base de données

-->  Impact

- Si ces critères ne sont pas respectés :
  - impact financier
  - impact sur la crédibilité
  - impact légal

-->  Solutions

- Suivre des recommandations : OWASP
- Utiliser les bonnes technologies : Spring Security

-->  Ce qu'il faut retenir

- La sécurité des applications web est une préoccupation constante
- Le niveau de sécurité peut s'évaluer en vérifiant les critères de :
  - confidentialité
  - disponibilité
  - intégrité
  - traçabilité
- La validation de ces critères implique :
  - de suivre des recommandations
  - d'utiliser les bonnes technologies
```

## C02 - L'authentification et l'autorisation dans les applications web :
```
-->  Contexte

- Deux concepts sont clés dans la sécurisation des applications web :
  - l'authentification
  - l'autorisation

-->  Authentification

- Définition : c'est la capacité de vérifier que l'utilisateur est bien qui il prétend être
- Illustration : la carte d'identité est un moyen d'identifier une personne

-->  Autorisation

- Définition : c'est la capacité de vérifier que l'utilisateur est en droit d'accéder à ce qu'il demande
- Illustration : un contrôleur vérifie que vous avez un billet de train valide prouvant que vous avez le droit d'être dans ce train, à cette place

-->  Combinaison

- Dans le cadre des applications web, il y a d'abord l'authentification puis l'autorisation

-->  Implémentation

- Le concept d'authentification se met en œuvre :
  - Soit via une authentification par session
  - Soit via une authentification par jeton
- Le concept d'autorisation se met en œuvre par l'utilisation :
  - De rôles
  - D'autorités

-->  Ce qu'il faut retenir

- La sécurité des applications web implique l'étape d'authentification puis d'autorisation
- L'authentification revient à vérifier que l'utilisateur est bien qui il prétend être
- L'autorisation revient à vérifier que l'utilisateur a bien le droit d'accéder à ce qu'il demande
```

## C03 - Découvrez les recommandations OWASP :
```
-->  OWASP


-->  OWASP

- L'Open Web Application Security Project (OWASP) est une communauté ouverte dédiée à permettre aux organisations de développer, acheter et maintenir des applications et des API fiables
- Source : owasp.org

-->  OWASP

- OWASP met à disposition de nombreuses ressources comme :
  - des outils
  - des recommandations
  - des articles de recherches

-->  TOP 10

- Liste des 10 vulnérabilités les plus critiques pour les applications web

-->  TOP 10 2021

- A01 : contrôles d'accès défaillants
- A02 : défaillances cryptographiques
- A03 : injection
- A04 : conception non sécurisée
- A05 : mauvaise configuration de sécurité
  - SECURITY BREACH
- A06 : composants vulnérables et obsolètes
  - UNSECURED
- A07 : identification et authentification de mauvaise qualité
- A08 : manque d'intégrité des données et du logiciel
  - Data Breach
- A09 : carence des systèmes de contrôle et de journalisation
  - ANALYSIS
- A10 : falsification de requêtes côté serveur
  - System Safety Compromised

-->  Méthode d'analyse du TOP 10

- Définition de la recommandation
- Examen des menaces
- Analyse des protections à mettre en œuvre
- Focus sur les points les plus importants

-->  Aller plus loin

- ASVS : Application Security Verification Standard
- Fournit une base pour tester les contrôles de sécurité et une liste d'attendus à respecter pour un développement sécurisé

-->  Ce qu'il faut retenir

- OWASP est un organisme mondial qui fait foi dans le cadre de la sécurité des applications web
- Le respect des 10 recommandations est le point de départ à la sécurisation d'une application
- Allez plus loin en explorant toutes les ressources qu'offre OWASP et en respectant ASVS
```

## C04 - Recommandation A01-2021 : Broken Access Control :
```
-->  Contrôles d'accès défaillants

- Les défaillances entraînent généralement la divulgation, la modification ou la destruction d'informations ou l'exécution d'une fonctionnalité métier en dehors des limites autorisées

-->  Menace 1

- Contournement des contrôles d'accès
  - En découvrant des URL
  - En modifiant l'URL (Insecure Direct Object Reference)

-->  Menace 2

- Accès à l'API à partir d'origines non autorisées à la suite de mauvaises configurations CORS (Cross-origin resource sharing)

-->  Menace 3

- Principe du moindre privilège non respecté
  - Accès normalement limité accordé à tous

-->  Protection à adopter

- Menace 1 : utiliser des références indirectes pour les ressources accessibles par les utilisateurs
- Menace 2 : minimiser l'utilisation de CORS
- Menace 3 : à l'exception des ressources publiques, tout doit être bloqué par défaut

-->  Ce qu'il faut retenir

- La première recommandation consiste à préserver les contrôles d'accès
- Les menaces reposent sur le contournement de ces contrôles ou l'exploitation de contrôles trop faibles
- Pour se prémunir, il faut bloquer par défaut les accès, limiter les accès autorisés au côté serveur et tracer les échecs
```

## C05 - Recommandation A02-2021 : cryptographic failure :
```
-->  Défaillances cryptographiques

- Les techniques cryptographiques ne sont pas ou sont partiellement mises en œuvre sur les données sensibles

-->  Menace 1

- Les données sensibles circulent sur le réseau en clair
- L'utilisation de protocoles non sécurisés comme HTTP ou FTP en est la cause

-->  Menace 2

- Les données sensibles sont stockées en clair ou en les chiffrant avec des algorithmes désuets

-->  Protection à adopter

- Pour résoudre les défaillances cryptographiques il faut :
  - Identifier les données sensibles
  - Agir sur le transfert de ces données sur le réseau
  - Agir sur le stockage de ces données

-->  Données sensibles

- Classifier les données traitées, stockées ou transmises par l'application pour identifier celles à caractère sensible

-->  Protocole sécurisé

- Des protocoles sécurisés doivent obligatoirement être utilisés, par exemple HTTPS
- Tout le réseau interne doit être sécurisé

-->  Stockage sécurisé

- Les données sensibles sont hachées
- Des algorithmes de hachage tel que SHA256 ou PBKDF2 sont utilisés

-->  Ce qu'il faut retenir

- Une donnée sensible ne doit pas transiter en clair
- Une donnée sensible ne doit pas être stockée en clair
- Il faut identifier les données sensibles
- Il faut mettre en œuvre des protocoles sécurisés comme HTTPS
- Il faut hacher les données sensibles avant de les stocker
```

## C06 - Recommandation A03-2021 : injection :
```
-->  Injection

- Insertion d'une donnée malveillante dans le but d'altérer un traitement

-->  Menace 1 : faille dans la validation des données

- L'application ne possède pas de processus de validation de la donnée

-->  Menace 2 : injection SQL

- Altération de la requête pour corrompre la donnée ou accéder à une donnée interdite

-->  Menace 3 : attaque XSS

- XSS : Cross-site Scripting
- Injection de script malveillants, par exemple en JavaScript

-->  Protection à adopter

- Mettre en place des revues de code source pour vérifier la validation des données
- Utiliser les requêtes préparées pour le SQL
- Échapper les caractères spéciaux

-->  Mise en œuvre

- Utiliser des technologies éprouvées qui ont des mécanismes de défense intégrés
- Par exemple :
  - Le framework Angular est paré pour les attaques XSS
  - Le framework Hibernate est paré pour les injections SQL

-->  Ce qu'il faut retenir

- Les menaces d'injection visent à accéder ou corrompre des données en modifiant un comportement de l'application
- L'utilisation des bonnes technologies est le meilleur rempart à ces menaces très connues
- La validation des données doit être une préoccupation constante du développeur
```

## C07 - Recommandation A04-2021 : insecure design :
```
-->  Conception non sécurisée

- Faille dans la conception de l'architecture des applications web
- Les problématiques de sécurité ne sont pas prises en compte avant le développement

-->  Cause

- Manque de compréhension technique des enjeux de sécurité à l'échelle de l'architecture
- Mauvaise identification des enjeux métiers et donc du niveau de sécurité adapté

-->  Menace

- Absence des contrôles de sécurité nécessaires
- Aucune implémentation sécurisée ne peut résoudre cette faille

-->  Protection à adopter

- Recenser les exigences métiers à travers l’examen des critères de sécurité (disponibilité, intégrité, confidentialité, traçabilité)
- Intégrer les exigences de sécurité fonctionnelles et techniques dans la définition des fonctionnalités (par exemple dans les US)

-->  Protection à adopter

- Mettre en œuvre un cycle de vie de développement sécurisé
- Valider la sécurité par des tests de différents niveaux (unitaires, intégrations, bout en bout)
- Appliquer et vérifier les contrôles de sécurité à chaque couche de l'architecture, tant au niveau infrastructure que logiciel

-->  Limite

- Une conception sécurisée ne garantit pas l'implémentation des mesures de sécurité associées

-->  Ce qu'il faut retenir

- Une conception non sécurisée ne peut se résoudre pas des implémentations sécurisées car il y aura des absences de contrôles de sécurité
- La question de la sécurité doit être une préoccupation de toutes les parties prenantes, qu'elles soient fonctionnelles ou techniques
```

## C08 - Recommandation A05-2021 : security misconfiguration :
```
-->  Mauvaise configuration de sécurité

- La configuration de sécurité est erronée, insuffisante ou désuète

-->  Couches non sécurisées

- Toutes les couches de l'application ne font pas l'objet d'une configuration de sécurité valide, offrant ainsi une porte d'accès à une attaque

-->  Fonctionnalités inutiles

- Les fonctionnalités non utiles sont actives (par exemple un port inutilisé est ouvert)

-->  Fuite d'informations

- La gestion des erreurs révèle trop d'informations permettant ainsi à un utilisateur malveillant de découvrir des aspects de la configuration de sécurité

-->  Protection à adopter

- Adopter un processus de durcissement de la sécurité répétable
- Appliquer un processus automatisé de vérification des configurations de sécurité
- Supprimer toutes fonctionnalités inutiles

-->  Ce qu'il faut retenir

- Une configuration de sécurité défaillante est une faille ouvrant une porte d'accès à votre système
- Les configurations de sécurité doivent faire l'objet d'un processus de durcissement répétable et automatisé
```

## C09 - Recommandation A06-2021 : Vulnerable and Outdated Components :
```
-->  Composants vulnérables et obsolètes

- Une tierce partie contenant une vulnérabilité est intégrée à votre architecture et exploitée pour mettre en danger la sécurité de votre application

-->  Menace

- Un composant tiers utilisé est vulnérable car il possède une ou plusieurs failles de sécurité
- Un composant tiers utilisé est obsolète car ses configurations de sécurité ne sont pas à jour
  - Par exemple, utilisation d'un algorithme de chiffrage désuet

-->  Menace : ces situations se produisent car...

- Les composants tiers utilisés directement ou indirectement sont méconnus des développeurs
- Les composants tiers utilisés ne sont pas mis à jour
- La compatibilité entre le code produit et les composants tiers utilisés n'est pas vérifiée

-->  Protection à adopter

- Vérifier les dépendances et supprimer les inutiles
- Vérifier en continu les versions et les mettre à jour pour bénéficier des dernières corrections de sécurité
- Utiliser des composants tiers éprouvés et crédibles sur l'aspect de la sécurité

-->  Ce qu'il faut retenir

- Une dépendance externe vulnérable est une porte d'entrée menaçant la sécurité d'une application web
- La négligence de l'équipe de développement est souvent la cause de cette menace
- Ces actions continues de vérification, mise à jour et suppression au niveau des composants tiers sont nécessaires
```

## C10 - Recommandation A07-2021 : Identification and Authentication Failures :
```
-->  Identification et authentification de mauvaise qualité

- L'application web contient des faiblesses lors de la phase d'authentification de l'utilisateur

-->  Menace

- Attaque automatisée permettant de tester une liste de noms d'utilisateurs et de mots de passe
- Les contraintes de définition de mots de passe sont faibles
- Les processus de récupération de mot de passe sont inefficaces (exemple : Questions secrètes)

-->  Menace

- Authentification multifacteur absente
- Invalidation de la session utilisateurs incorrect

-->  Protection à adopter

- Liste des protections
  - MFA
  - Règles strictes de définition de mots de passe et pas d’informations par défaut
  - Gestion de la session côté serveur

-->  Ce qu'il faut retenir

- Une procédure d'authentification des utilisateurs faible est une porte ouverte pour la récupération de données sensibles
- Il ne faut pas se limiter à des mesures de sécurité basique
- Se protéger implique des solutions comme MFA et des règles strictes de définition de mots de passe
```

## C11 - Recommandation A08-2021 : Software and Data Integrity Failures :
```
-->  Manque d'intégrité des données et du logiciel

- Les données ou les composants sollicités ne sont pas vérifiés
- L'intégrité de ces derniers n'est pas garantie

-->  Menace

- La mise à jour d'un composant tiers ne provient pas de la source officielle et menace la sécurité de votre application

-->  Menace

- La chaîne de build n'est pas sécurisée et autorise un accès non autorisé, un code malveillant ou la compromission du système

-->  Protection à adopter

- Vérifier la configuration des outils de gestion des dépendances
- Par exemple : Maven utilise-t-il les dépôts de confiance

-->  Protection à adopter

- La chaîne de build dispose d'une ségrégation, d'une configuration et d'un contrôle d'accès approprié

-->  Ce qu'il faut retenir

- L'intégrité d'une donnée ou d'un logiciel n'est pas automatiquement garanti
- Une donnée ou un logiciel dont l'intégrité est corrompue est une menace directe sur la sécurité d'une application web
- Se prémunir implique d'établir des contrôles sur l'état des données et des logiciels sollicités
```

## C12 - Recommandation A09-2021 : Security Logging and Monitoring Failures :
```
-->  Carence des systèmes de contrôle et de journalisation

- Le code de l'application web ne permet pas de récolter les données nécessaires pour identifier les problèmes de sécurité

-->  Menace

- Des problèmes de sécurité sont détectables mais non tracés, empêchant ainsi leur résolution

-->  Menace

- Les journaux ne sont accessibles que localement et donc difficilement consultables

-->  Menace

- L'absence d'alertes en temps réel empêche une réaction immédiate pour se protéger d'une attaque

-->  Protection à adopter

- Établir une politique de journalisation avec des niveaux définis et connus des développeurs

-->  Protection à adopter

- Enregistrer les journaux dans un format standard et les rendre accessibles à un système centralisé

-->  Protection à adopter

- La supervision de l'état de l'application doit comporter des alertes en temps réel

-->  Ce qu'il faut retenir

- La journalisation est un élément critique de la lutte contre les attaques
- Une faille d'enregistrement ou d'accès aux journaux rendrait aveugles les personnes chargées de veiller à la sécurité de l'application web
- Une stratégie de journalisation et la centralisation des journaux sont indispensables
```

## C13 - Recommandation A10-2021 : Server-Side Request Forgery (SSRF) :
```
-->  Falsification de requête côté serveur

- Une application web est contrainte à envoyer une requête à une destination non prévue

-->  Menace

- L'application web manipulée devient une porte d'entrée permettant de contourner des protections comme un pare-feu

-->  Protection à adopter

- La segmentation du réseau en refusant par défaut tout trafic
- Validation des entrées et désactivation des redirections HTTP
- Ne pas envoyer de réponses brutes au client

-->  Ce qu'il faut retenir

- La manipulation malveillante d'une application web pour exécuter une requête non prévue est une menace très impactante
- Les protections s'appliquent tant au niveau réseau que applicatif
- La validation des données est de nouveau critique pour se prémunir contre ces failles
```

## C14 - Mise en œuvre de Spring Security dans un projet Java Spring Boot :
```
-->  Spring Security


-->  Contexte technologique

- Langage de programmation : JAVA
- Framework : Spring
- Module : Spring Security

-->  Objectif

- Sécuriser une application web
- Cadre d'application : sécuriser une API

-->  Mécanisme de Spring Security

- Client
- FilterChain :
  - Filter₀
  - DelegatingFilterProxy
    - FilterChainProxy
  - Filter₂
  - Servlet
- SecurityFilterChain :
  - Security Filter₀
  - …
  - Security Filterₙ

-->  Configuration par défaut

- Toutes les routes de l'application sont sécurisées
- Un seul utilisateur existe, il est nommé « user »
- Le mot de passe de cet utilisateur est généré au démarrage de l'application et affiché dans la console
- Différentes protections sont activées (par exemple : contre les attaques CSRF)

-->  Authentification par session

- Après l'authentification de l'utilisateur, une session est créée côté serveur
- Côté navigateur, des informations liées à la session sont conservées
- À chaque nouvelle requête, les informations du client et du serveur sont comparées

-->  Ce qu'il faut retenir

- Spring Security est un outil performant pour sécuriser une application web
- Le mécanisme de Spring Security repose sur la mise en œuvre d’une chaîne de filtres de sécurité
- Une configuration par défaut est appliquée sur tout projet Spring Boot ajoutant le starter Spring Security
```

## C15 - Configurer une chaîne de filtres de sécurité « Basic Authentication » :
```
-->  Objectif

- Adapter la configuration par défaut de Spring Security pour définir des routes publiques ou privées

-->  Ce qu'il faut retenir

- Création d'une classe dédiée à la configuration de Spring Security
- Manipulation de la classe HttpSecurity pour mettre à disposition un bean SecurityFilterChain
- Possibilité d'indiquer les routes accessibles sans authentification ou non
```

## C16 - Utiliser des utilisateurs en base de données pour l'authentification :
```
-->  Objectif

- Adapter la configuration par défaut de Spring Security pour authentifier un utilisateur selon une base de données

-->  Ce qu'il faut retenir

- L'interface UserDetailsService doit être implémentée pour créer une classe capable de récupérer un utilisateur dans la base de données
- La configuration de sécurité doit être modifiée pour fournir à l'Authentification Manager la nouvelle classe
```

## C17 - Gérer l'autorisation grâce à la mise en œuvre de rôles de sécurité :
```
-->  Objectif

- Mettre en place un processus d'autorisation en se basant sur des rôles

-->  Ce qu'il faut retenir

- Un utilisateur est autorisé grâce à des rôles ou des autorités
- La chaîne de filtres de sécurité permet d'indiquer les rôles ou autorités nécessaires pour accéder à une route
```

## C18 - L'authentification basée sur les jetons :
```
-->  Objectif

- Utiliser un jeton pour authentifier et autoriser un utilisateur et non la session

-->  Fonctionnement

- L'utilisateur s'authentifie et l'application renvoie un jeton
- À chaque nouvelle requête, l'utilisateur renvoie le jeton et le serveur vérifie ce dernier

-->  Authentification par jeton

- Avantages
  - Mécanisme sans état
  - Sécurité accrue
- Inconvénients
  - Complexité technique

-->  JWT

- JSON Web Token
- Objet pour encoder et transmettre les informations d'authentification et d'autorisation

-->  Mise en œuvre

- Solution 1 : Module OAuth2 Resource Server de Spring
- Solution 2 : Créer son propre filtre de sécurité

-->  Ce qu'il faut retenir

- Une authentification basée sur les jetons sera un choix privilégié pour protéger une API
- JWT est l'outil le plus répandu pour ce mode d'authentification
- Plusieurs solutions techniques sont possibles
```

## C19 - Configurer une chaîne de filtres de sécurité « Bearer Token Authentication » :
```
-->  Objectif

- Mettre en place une authentification par jeton grâce à OAuth2 Resource Server

-->  Ce qu'il faut retenir

- OAuth2 Resource Server offre un mécanisme complet d'authentification par jeton
- Le développeur doit veiller à la robustesse de la clé secrète utilisée pour le chiffrement
```

## C20 - Créer votre propre filtre de sécurité basé sur les jetons :
```
-->  Objectif

- Créer son propre filtre de sécurité pour une authentification par token

-->  Ce qu'il faut retenir

- Spring Security permet d’ajouter ses propres filtres à la chaîne de filtres de sécurité
- Une bibliothèque externe pour gérer un JWT est nécessaire
- Le développeur doit s’assurer de maîtriser le code réalisé
```

## C21 - Testez votre sécurité avec Spring Security Test :
```
-->  Objectif

- Utiliser Spring Boot Test et Spring Security Test pour valider la configuration de sécurité

-->  Ce qu'il faut retenir

- `@WithMockUser` est une annotation utile pour tester la configuration de sécurité
- Spring Security Test fournit des fonctionnalités pour vérifier le comportement de l’application
- Testez également les cas d’erreurs et pas uniquement un succès d’authentification
```

## C22 - Découvrez le protocole d'autorisation OAuth2 :
```
-->  Contexte

- Gérer l’authentification et l’autorisation de façon sécurisée est un vrai défi !
- Pour faire face à ce défi, on peut s’appuyer sur des structures fiables
- Vous êtes-vous déjà connecté à une application web à partir d’un compte Google, Facebook ou autre ?
- Dans ce cas, l’authentification a été déléguée à une entreprise vérifiée

-->  Entreprise vérifiée

- Cela s’appelle un fournisseur d’identité (IdP)
- Exemple : Google

-->  Protocole d’autorisation

- Le protocole d’autorisation OAuth permet :
  - À l’IdP d’authentifier l’utilisateur
  - À l’IdP d’autoriser l’utilisation de certaines informations par l’application web

-->  Flux

- Acteurs :
  - Navigateur
  - Application web
  - IdP
- Navigateur → Application web : Puis je me connecter ?
- Application web → Navigateur : Tu dois t’authentifier sur l’IdP
- Navigateur → IdP : Peux tu m’authentifier et me donner un code d’autorisation ?
- IdP → Navigateur : Tu es authentifié et voici ton code d’autorisation
- Navigateur → Application web : C’est bon je suis authentifié et voici le code d’autorisation
- Application web → IdP : Est ce que ce code d’autorisation est valide ?
- IdP → Application web : Oui, voici un jeton d’accès
- Application web → IdP : Peux tu me donner les informations utilisateurs associées à ce jeton d’accès ?
- IdP → Application web : Voici les informations auxquelles tu peux accéder
- Application web → Navigateur : C’est bon tu es connecté et je sais que tu es un utilisateur valide

-->  Points techniques notables

- La connexion vers l’IdP est sécurisée
- Des jetons sans état sont utilisés

-->  Ce qu'il faut retenir

- OAuth est un protocole d’autorisation très répandu pour sécuriser des applications web
- Un fournisseur d’identité est nécessaire pour sa mise en œuvre
- L’authentification est déléguée chez l’IdP
- L’application web est autorisée à accéder à certaines informations de l’utilisateur par l’IdP
```

## C23 - Découvrez le protocole d'identité OpenID :
```
-->  Contexte

- OAuth est utilisé comme protocole d’autorisation dans votre application web
- Rappel : l’utilisateur n’est pas authentifié sur l’application web mais chez le fournisseur d’identité

-->  Problématique

- Comment permettre à l’application web d’accéder aux informations et prouver l’identité de l’utilisateur ?
- Ce qui revient à l’authentifier

-->  OpenID Connect

- OIDC est un protocole d’identité
- Il permet à l’application web d’avoir un jeton d’identité chiffré contenant les informations protégées de l’utilisateur

-->  Flux

- Acteurs :
  - Navigateur
  - Application web
  - IdP
- Navigateur → Application web : Puis je me connecter ?
- Application web → Navigateur : Tu dois t’authentifier sur l’IdP avec un scope OIDC
- Navigateur → IdP : Peux tu m’authentifier et me donner un code d’autorisation ?
- IdP → Navigateur : Tu es authentifié et voici ton code d’autorisation
- Navigateur → Application web : C’est bon je suis authentifié et voici le code d’autorisation
- Application web → IdP : Est ce que ce code d’autorisation est valide ?
- IdP → Application web : Oui, voici un jeton d’accès et un token d’identité
- Application web → IdP : Peux tu me donner les informations utilisateurs associées à ce jeton d’accès ?
- IdP → Application web : Voici les informations auxquelles tu peux accéder
- Application web → IdP : Peux tu me donner les informations utilisateurs protégées grâce à ce jeton d’identité ?
- IdP → Application web : Voici les informations auxquelles tu peux accéder
- Application web → Navigateur : C’est bon tu es connecté et je sais que tu es un utilisateur valide

-->  Points techniques notables

- Le jeton d’identité est un JWT
- Les informations protégées fournies dépendent du scope requis (exemple : `openid email`)
- OIDC fonctionne avec OAuth 2

-->  Ce qu'il faut retenir

- OIDC étend OAuth2
- OIDC est un protocole d’identité renforçant la sécurité grâce à des jetons d’identité chiffrés
- JWT est utilisé pour les jetons d’identité
- L’accès à des informations utilisateurs protégées est permis
```

## C24 - Reprise des points clés :
```
-->  Enjeu

- La sécurité des applications web est un enjeu majeur
- Le nombre d’attaques est en expansion, que ce soit sur des grandes ou petites structures

-->  OWASP

- OWASP accompagne les entreprises pour obtenir des applications web sécurisées
- Le point de départ est de suivre les recommandations du TOP 10 OWASP

-->  TOP 10 2021

- A01 : Contrôles d’accès défaillants
- A02 : Défaillances cryptographiques
- A03 : Injection
- A04 : Conception non sécurisée
- A05 : Mauvaise configuration de sécurité
- A06 : Composants vulnérables et obsolètes
- A07 : Identification et authentification de mauvaise qualité
- A08 : Manque d’intégrité des données et du logiciel
- A09 : Carence des systèmes de contrôle et de journalisation
- A10 : Falsification de requête côté serveur (SSRF)

-->  Framework

- La mise en œuvre des recommandations de sécurité implique l’utilisation des bons Frameworks
- Durant ce MOOC : Spring Security

-->  Spring Security

- Définition d’une chaîne de filtres de sécurité configurable et permettant :
  - d’authentifier
  - d’autoriser

-->  Authentification par session

- Simple
- Informations partagées entre le client et le serveur

-->  Authentification par jeton

- Plus complexe
- Plus sécurisé qu’une authentification par session
- Informations uniquement côté client

-->  OAuth 2.0

- Protocole d’autorisation
- Délégation de l’authentification à un fournisseur d’identité
- Un jeton d’accès permet à l’application web d’accéder à des informations non protégées

-->  OpenID Connect

- Protocole d’identité
- Un jeton d’identité permet à l’application web d’accéder à des informations

-->  Ce qu'il faut retenir

- La sécurisation des applications web doit être une de vos compétences !
- Allez plus loin en explorant dans le détail chaque notion du MOOC
```