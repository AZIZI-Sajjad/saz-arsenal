# BAC+3-B02-M01-CMD

#plateform/VISIPLUS
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/DEVOPS
## Lister toutes les bases existantes
```
SHOW DATABASES;
```

## Créer une base de données si elle n'existe pas
```
CREATE DATABASE IF NOT EXISTS <base>;
```

## Créer une base de données avec encodage et collation
```
CREATE DATABASE IF NOT EXISTS <base> CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

## Afficher la définition complète d'une base
```
SHOW CREATE DATABASE <base>;
```

## Sélectionner la base de travail
```
USE <base>;
```

## Supprimer une base
```
DROP DATABASE <base>;
```

## Créer une table (syntaxe générale)
```
CREATE TABLE <table> (<attribut1> <type_attribut1> <contrainte>, <attribut2> <type_attribut2>);
```

## Créer une table avec clé primaire auto-incrémentée
```
CREATE TABLE <table> (<id> INT AUTO_INCREMENT PRIMARY KEY, <colonne> VARCHAR(<taille>));
```

## Exemple - table CLIENT avec contraintes NOT NULL / UNIQUE / DEFAULT
```
CREATE TABLE CLIENT (id_client INT NOT NULL AUTO_INCREMENT PRIMARY KEY, nom VARCHAR(50) NOT NULL, prenom VARCHAR(50) NOT NULL, email VARCHAR(150) NOT NULL UNIQUE, pays VARCHAR(50) DEFAULT 'France', date_inscription DATE DEFAULT (CURDATE()));
```

## Contrainte CHECK sur le format d'un email
```
CREATE TABLE CLIENT (id_client INT NOT NULL AUTO_INCREMENT PRIMARY KEY, email VARCHAR(150) NOT NULL UNIQUE, CHECK (email LIKE '%_@%._%'));
```

## Clé primaire composite
```
CREATE TABLE <table> (<col1> INT, <col2> INT, PRIMARY KEY (<col1>, <col2>));
```

## Clé étrangère
```
FOREIGN KEY (<colonne>) REFERENCES <table_ref>(<colonne_ref>)
```

## Clé étrangère avec actions en cascade
```
FOREIGN KEY (<colonne>) REFERENCES <table_ref>(<colonne_ref>) ON UPDATE CASCADE ON DELETE CASCADE
```

## Exemple - table LIGNE_COMMANDE (PK composite + 2 FK)
```
CREATE TABLE LIGNE_COMMANDE (id_commande INT, id_produit INT, quantite INT, prix_unitaire DECIMAL(10,2), PRIMARY KEY (id_commande, id_produit), FOREIGN KEY (id_commande) REFERENCES COMMANDE(id_commande), FOREIGN KEY (id_produit) REFERENCES PRODUIT(id_produit));
```

## Exemple - contraintes nommées (pk_ / chk_ / fk_)
```
CREATE TABLE PRODUIT (id_produit INT NOT NULL AUTO_INCREMENT, nom VARCHAR(100) NOT NULL, descriptif TEXT, prix DECIMAL(10,2) NOT NULL, stock INT NOT NULL DEFAULT 0, date_ajout DATE, id_categorie INT NOT NULL, CONSTRAINT pk_produit PRIMARY KEY (id_produit), CONSTRAINT chk_produit_prix CHECK (prix >= 0), CONSTRAINT chk_produit_stock CHECK (stock >= 0), CONSTRAINT fk_produit_categorie FOREIGN KEY (id_categorie) REFERENCES CATEGORIE(id_categorie));
```

## Sauvegarder une base avant modification (terminal)
```
mysqldump -u <user> -p <base> > <fichier_backup>.sql
```

## Copie temporaire d'une table avant modification
```
CREATE TABLE <table>_backup_<date> AS SELECT * FROM <table>;
```

## Supprimer une table
```
DROP TABLE IF EXISTS <table>;
```

## Renommer une table
```
RENAME TABLE <ancien_nom> TO <nouveau_nom>;
```

## Ajouter une colonne
```
ALTER TABLE <table> ADD <colonne> <type> <contraintes>;
```

## Ajouter une colonne NOT NULL avec valeur par défaut
```
ALTER TABLE <table> ADD <colonne> <type> NOT NULL DEFAULT '<valeur>';
```

## Ajouter une contrainte UNIQUE
```
ALTER TABLE <table> ADD CONSTRAINT <uq_table_col> UNIQUE (<colonne>);
```

## Ajouter une clé étrangère
```
ALTER TABLE <table> ADD CONSTRAINT <fk_table_ref> FOREIGN KEY (<colonne>) REFERENCES <table_ref>(<colonne_ref>);
```

## Modifier le type / les contraintes d'une colonne
```
ALTER TABLE <table> MODIFY <colonne> <nouveau_type> <contraintes>;
```

## Renommer une colonne (et redéfinir son type)
```
ALTER TABLE <table> CHANGE <ancien_nom> <nouveau_nom> <type> <contraintes>;
```

## Exemple - CHANGE avec ENUM
```
ALTER TABLE commande CHANGE statut statut_commande ENUM('en attente', 'expédiée', 'livrée', 'annulée') NOT NULL DEFAULT 'en attente';
```

## Supprimer une colonne (irréversible)
```
ALTER TABLE <table> DROP COLUMN <colonne>;
```

## Supprimer une contrainte
```
ALTER TABLE <table> DROP <nom_contrainte>;
```

## Insérer une ligne en précisant les colonnes
```
INSERT INTO <table> (<col1>, <col2>) VALUES ('<val1>', '<val2>');
```

## Insérer plusieurs lignes
```
INSERT INTO <table> (<col1>, <col2>) VALUES ('<val1>', '<val2>'), ('<val3>', '<val4>');
```

## Mettre à jour une ligne ciblée
```
UPDATE <table> SET <colonne> = '<valeur>' WHERE <id> = <valeur_id>;
```

## Mettre à jour plusieurs colonnes
```
UPDATE <table> SET <col1> = '<val1>', <col2> = '<val2>' WHERE <id> = <valeur_id>;
```

## Vérifier la ligne avant UPDATE / DELETE
```
SELECT * FROM <table> WHERE <id> = <valeur_id>;
```

## Supprimer une ligne ciblée
```
DELETE FROM <table> WHERE <id> = <valeur_id>;
```

## Vider une table (réinitialise l'AUTO_INCREMENT)
```
TRUNCATE TABLE <table>;
```

## Démarrer une transaction
```
START TRANSACTION;
```

## Valider une transaction
```
COMMIT;
```

## Annuler une transaction
```
ROLLBACK;
```

## Récupérer l'id de la dernière insertion dans une variable
```
SET @<variable> = LAST_INSERT_ID();
```

## Lire toutes les colonnes
```
SELECT * FROM <table>;
```

## Lire des colonnes précises
```
SELECT <col1>, <col2> FROM <table>;
```

## Filtrer avec WHERE et opérateurs logiques
```
SELECT * FROM <table> WHERE <condition1> AND <condition2>;
```

## Filtrer sur une liste de valeurs (IN)
```
SELECT * FROM <table> WHERE <colonne> IN (<val1>, <val2>);
```

## Filtrer sur un intervalle (BETWEEN)
```
SELECT * FROM <table> WHERE <colonne> BETWEEN <min> AND <max>;
```

## Filtrer sur un motif texte (LIKE)
```
SELECT <colonne> FROM <table> WHERE <colonne> LIKE '<motif>';
```

## Filtrer les emails invalides
```
SELECT * FROM <table> WHERE email NOT LIKE '_%@_%.__%';
```

## Filtrer les valeurs NULL
```
SELECT <colonne> FROM <table> WHERE <colonne> IS NULL;
```

## Filtrer les valeurs non NULL
```
SELECT <colonne> FROM <table> WHERE <colonne> IS NOT NULL;
```

## Trier les résultats
```
SELECT <colonnes> FROM <table> ORDER BY <colonne> DESC;
```

## Trier sur plusieurs colonnes
```
SELECT <colonnes> FROM <table> ORDER BY <col1>, <col2>;
```

## Top N (tri + LIMIT)
```
SELECT <colonnes> FROM <table> ORDER BY <colonne> DESC LIMIT <n>;
```

## Supprimer les doublons
```
SELECT DISTINCT <colonne> FROM <table>;
```

## Compter les lignes
```
SELECT COUNT(*) FROM <table>;
```

## Somme calculée (chiffre d'affaires)
```
SELECT SUM(prix_unitaire * quantite) AS CA FROM ligne_commande;
```

## Moyenne / minimum / maximum
```
SELECT AVG(<colonne>), MIN(<colonne>), MAX(<colonne>) FROM <table>;
```

## Regrouper avec GROUP BY
```
SELECT <colonne_groupe>, <fonction_agregation>(<colonne>) FROM <table> GROUP BY <colonne_groupe>;
```

## Filtrer les groupes avec HAVING
```
SELECT <colonne_groupe>, COUNT(*) FROM <table> GROUP BY <colonne_groupe> HAVING COUNT(*) > <n>;
```

## Condition CASE WHEN
```
CASE WHEN <condition1> THEN <valeur1> WHEN <condition2> THEN <valeur2> ELSE <valeur_par_defaut> END
```

## Exemple - classer les commandes par type de livraison
```
SELECT CASE WHEN frais_livraison = 0 THEN 'Livraison gratuite' WHEN frais_livraison < 5 THEN 'Livraison économique' WHEN frais_livraison BETWEEN 5 AND 10 THEN 'Livraison standard' ELSE 'Livraison express' END AS type_livraison, COUNT(*) AS nb_commandes FROM commande_client GROUP BY type_livraison;
```

## Jointure entre deux tables
```
SELECT <colonnes> FROM <table1> JOIN <table2> ON <table1>.<col1> = <table2>.<col2>;
```

## Jointure avec alias
```
SELECT c.nom, cc.id_commande FROM client AS c JOIN commande_client AS cc ON c.id_client = cc.id_client;
```

## LEFT JOIN
```
SELECT <colonnes> FROM <table1> LEFT JOIN <table2> ON <table1>.<col1> = <table2>.<col2>;
```

## RIGHT JOIN
```
SELECT <colonnes> FROM <table1> RIGHT JOIN <table2> ON <table1>.<col1> = <table2>.<col2>;
```

## Exemple - jointure sur 4 tables
```
SELECT c.nom AS client, p.nom AS produit, lc.quantite FROM client AS c JOIN commande_client AS cc ON c.id_client = cc.id_client JOIN ligne_commande AS lc ON cc.id_commande = lc.id_commande JOIN produit AS p ON lc.id_produit = p.id_produit;
```

## Exemple - top 5 clients par nombre de commandes
```
SELECT c.nom, c.prenom, COUNT(cc.id_commande) AS nb_commandes FROM client AS c JOIN commande_client AS cc ON c.id_client = cc.id_client GROUP BY c.id_client, c.nom, c.prenom ORDER BY nb_commandes DESC LIMIT 5;
```

## Sous-requête dans WHERE
```
SELECT <colonnes> FROM <table> WHERE <colonne> IN (SELECT <colonne> FROM <table2>);
```

## Exemple - produits jamais commandés
```
SELECT nom, prix, stock FROM produit WHERE id_produit NOT IN (SELECT DISTINCT id_produit FROM ligne_commande);
```

## Sous-requête dans FROM
```
SELECT id_commande, total_commande FROM (SELECT id_commande, SUM(quantite * prix_unitaire) AS total_commande FROM ligne_commande GROUP BY id_commande) AS ca_par_commande WHERE total_commande > 100 ORDER BY total_commande DESC;
```

## Sous-requête dans SELECT
```
SELECT id_produit, nom, prix, stock, (SELECT SUM(quantite) FROM ligne_commande WHERE ligne_commande.id_produit = produit.id_produit) AS total_vendu FROM produit ORDER BY total_vendu DESC;
```

## Arrondir / tronquer
```
SELECT ROUND(<valeur>, <decimales>), TRUNCATE(<valeur>, <decimales>);
```

## Arrondi supérieur / inférieur
```
SELECT CEIL(<valeur>), FLOOR(<valeur>);
```

## Valeur absolue, modulo, puissance, racine carrée
```
SELECT ABS(<valeur>), MOD(<a>, <b>), POWER(<base>, <exposant>), SQRT(<valeur>);
```

## Exemple - prix TTC
```
SELECT nom, prix, ROUND(prix * 1.20, 2) AS prix_ttc FROM produit LIMIT 3;
```

## Nombre aléatoire
```
SELECT RAND();
```

## Lignes aléatoires
```
SELECT * FROM <table> ORDER BY RAND() LIMIT <n>;
```

## Minuscules / majuscules
```
SELECT LOWER(<colonne>), UPPER(<colonne>) FROM <table>;
```

## Supprimer les espaces
```
SELECT TRIM(<colonne>), LTRIM(<colonne>), RTRIM(<colonne>) FROM <table>;
```

## Concaténer
```
SELECT CONCAT(prenom, ' ', nom) AS nom_complet FROM client;
```

## Concaténer avec séparateur (ignore les NULL)
```
SELECT CONCAT_WS('<separateur>', <col1>, <col2>) FROM <table>;
```

## Remplacer l'affichage des NULL
```
SELECT COALESCE(<colonne>, '<valeur_si_null>') FROM <table>;
```

## Extraire une partie du texte
```
SELECT SUBSTRING('<texte>', <debut>, <longueur>);
```

## Position d'un motif dans un texte
```
SELECT LOCATE('<motif>', '<texte>');
```

## Longueur en octets / en caractères
```
SELECT LENGTH('<texte>'), CHAR_LENGTH('<texte>');
```

## Remplacer du texte
```
SELECT REPLACE(<texte>, '<motif_a_remplacer>', '<nouveau_motif>');
```

## Date et heure actuelles
```
SELECT NOW(), CURDATE(), CURTIME();
```

## Filtrer sur une période (DATETIME)
```
SELECT * FROM <table> WHERE <colonne_date> >= '<YYYY-MM-DD>' AND <colonne_date> < '<YYYY-MM-DD>';
```

## Extraire année / mois / jour
```
SELECT YEAR(<colonne_date>), MONTH(<colonne_date>), DAY(<colonne_date>) FROM <table>;
```

## Formater une date
```
SELECT DATE_FORMAT(<colonne_date>, '%d/%m/%Y') AS date_fr FROM <table>;
```

## Ajouter un intervalle à une date
```
SELECT DATE_ADD(<colonne_date>, INTERVAL <n> DAY) FROM <table>;
```

## Retirer un intervalle à une date
```
SELECT DATE_SUB(CURDATE(), INTERVAL <n> YEAR);
```

## Écart en jours entre deux dates
```
SELECT DATEDIFF(NOW(), <colonne_date>) AS nb_jours FROM <table>;
```

## Créer un utilisateur
```
CREATE USER '<utilisateur>'@'<hote>' IDENTIFIED BY '<mot_de_passe>';
```

## Lister les utilisateurs
```
SELECT user, host FROM mysql.user;
```

## Donner des droits sur une base
```
GRANT SELECT, INSERT, UPDATE ON <base>.* TO '<utilisateur>'@'<hote>';
```

## Donner tous les droits sur une base
```
GRANT ALL PRIVILEGES ON <base>.* TO '<utilisateur>'@'<hote>';
```

## Retirer des droits
```
REVOKE <privilege> ON <cible> FROM '<utilisateur>'@'<hote>';
```

## Supprimer un utilisateur
```
DROP USER '<utilisateur>'@'<hote>';
```

## Requête préparée (PHP / PDO)
```
$stmt = $pdo->prepare("SELECT * FROM client WHERE email = ?"); $stmt->execute([$email]);
```

## Requête préparée (Python)
```
cursor.execute("SELECT * FROM client WHERE email = %s", (email,))
```

## Créer un index
```
CREATE INDEX <nom_index> ON <table>(<colonne>);
```

## Créer une vue
```
CREATE VIEW <nom_vue> AS SELECT <colonnes> FROM <table>;
```

## Créer un trigger (mise à jour auto d'une date de modification)
```
CREATE TRIGGER maj_date_modification BEFORE UPDATE ON commande_client FOR EACH ROW SET NEW.date_modification = NOW();
```