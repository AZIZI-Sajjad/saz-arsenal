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

## Cours - Créer la base ecommerce (utf8mb4 + comparaison sans casse ni accents)
```
CREATE DATABASE IF NOT EXISTS ecommerce CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
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

## Cours - Table CLIENT (types seuls, sans clé ni contrainte)
```
CREATE TABLE CLIENT (id_client INT, nom VARCHAR(50), prenom VARCHAR(50), email VARCHAR(150), pays VARCHAR(50), date_inscription DATE);
```

## Cours - Table CLIENT avec clé primaire auto-incrémentée
```
CREATE TABLE CLIENT (id_client INT auto_increment PRIMARY KEY, nom VARCHAR(50), prenom VARCHAR(50), email VARCHAR(150), pays VARCHAR(50), date_inscription DATE);
```

## Cours - Table CLIENT avec NOT NULL (champs obligatoires)
```
CREATE TABLE CLIENT (id_client INT NOT NULL AUTO_INCREMENT PRIMARY KEY, nom VARCHAR(50) NOT NULL, prenom VARCHAR(50) NOT NULL, email VARCHAR(150) NOT NULL, pays VARCHAR(50), date_inscription DATE);
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

## Cours - LIGNE_COMMANDE avec clé primaire composite (couple commande + produit unique)
```
CREATE TABLE LIGNE_COMMANDE (id_commande INT, id_produit INT, quantite INT, prix_unitaire DECIMAL(10,2), PRIMARY KEY (id_commande, id_produit));
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

## Cours - Sauvegarde de la base ecommerce (terminal)
```
mysqldump -u root -p ecommerce > backup_ecommerce_20260508.sql
```

## Copie temporaire d'une table avant modification
```
CREATE TABLE <table>_backup_<date> AS SELECT * FROM <table>;
```

## Cours - Copie de la table client avant modification
```
CREATE TABLE client_backup_20260508 AS SELECT * FROM client;
```

## Supprimer une table
```
DROP TABLE IF EXISTS <table>;
```

## Renommer une table
```
RENAME TABLE <ancien_nom> TO <nouveau_nom>;
```

## Cours - Renommer commande en commande_client
```
RENAME TABLE commande TO commande_client;
```

## Ajouter une colonne
```
ALTER TABLE <table> ADD <colonne> <type> <contraintes>;
```

## Cours - Ajouter une colonne téléphone
```
ALTER TABLE client ADD telephone CHAR(10);
```

## Ajouter une colonne NOT NULL avec valeur par défaut
```
ALTER TABLE <table> ADD <colonne> <type> NOT NULL DEFAULT '<valeur>';
```

## Cours - Ajouter téléphone NOT NULL avec valeur par défaut (lignes existantes remplies)
```
ALTER TABLE client ADD telephone CHAR(10) NOT NULL DEFAULT "XXXXXXXXXX";
```

## Ajouter une contrainte UNIQUE
```
ALTER TABLE <table> ADD CONSTRAINT <uq_table_col> UNIQUE (<colonne>);
```

## Cours - Rendre l'email unique (échoue si des doublons existent)
```
ALTER TABLE client ADD CONSTRAINT uq_client_email UNIQUE (email);
```

## Ajouter une clé étrangère
```
ALTER TABLE <table> ADD CONSTRAINT <fk_table_ref> FOREIGN KEY (<colonne>) REFERENCES <table_ref>(<colonne_ref>);
```

## Cours - Ajouter la FK ligne_commande -> commande_client
```
ALTER TABLE ligne_commande ADD CONSTRAINT fk_ligne_commande_commande_client FOREIGN KEY (id_commande) REFERENCES commande_client(id_commande);
```

## Modifier le type / les contraintes d'une colonne
```
ALTER TABLE <table> MODIFY <colonne> <nouveau_type> <contraintes>;
```

## Cours - Passer nom à 100 caractères obligatoire
```
ALTER TABLE client MODIFY nom VARCHAR(100) NOT NULL;
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

## Cours - Supprimer la colonne pays (syntaxe courte)
```
ALTER TABLE client DROP pays;
```

## Supprimer une contrainte
```
ALTER TABLE <table> DROP <nom_contrainte>;
```

## Cours - Modifier une contrainte : supprimer puis recréer
```
ALTER TABLE client DROP uq_client_email; ALTER TABLE client ADD CONSTRAINT uq_client_email UNIQUE (email);
```

## Insérer une ligne en précisant les colonnes
```
INSERT INTO <table> (<col1>, <col2>) VALUES ('<val1>', '<val2>');
```

## Insérer sans préciser les colonnes (ordre exact de la table)
```
INSERT INTO <table> VALUES ('<val1>', '<val2>');
```

## Insérer plusieurs lignes
```
INSERT INTO <table> (<col1>, <col2>) VALUES ('<val1>', '<val2>'), ('<val3>', '<val4>');
```

## Cours - Remplir la table CATEGORIE en un seul INSERT
```
INSERT INTO CATEGORIE (nom, description) VALUES ('Électronique', 'Smartphones, ordinateurs, tablettes et accessoires high-tech'), ('Mode', 'Vêtements, chaussures et accessoires de mode'), ('Maison', 'Décoration, mobilier et équipements pour la maison'), ('Sport', 'Équipements et vêtements de sport et loisirs'), ('Beauté', 'Cosmétiques, soins et parfums'), ('Livres', 'Romans, essais, manuels et livres numériques'), ('Jouets', 'Jeux et jouets pour enfants de tous âges'), ('Alimentation', 'Produits alimentaires, épicerie fine et boissons');
```

## Cours - INSERT client (telephone prend sa valeur par défaut)
```
INSERT INTO CLIENT (nom, prenom, email, date_inscription) VALUES ('Martin', 'Sophie', 'sophie.martin@gmail.com', '2023-03-15');
```

## Mettre à jour une ligne ciblée
```
UPDATE <table> SET <colonne> = '<valeur>' WHERE <id> = <valeur_id>;
```

## Mettre à jour plusieurs colonnes
```
UPDATE <table> SET <col1> = '<val1>', <col2> = '<val2>' WHERE <id> = <valeur_id>;
```

## Cours - Modifier email et téléphone du client 1
```
UPDATE client SET email = 'martin@gmail.com', telephone = '0728654512' WHERE id_client = 1;
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

## Cours - Transaction complète : commande + lignes + stock, tout ou rien
```
START TRANSACTION; INSERT INTO commande (date_commande, statut, frais_livraison, adresse_livraison, id_client) VALUES (NOW(), 'en_attente', 5.99, '12 rue de la Paix, Paris', 1); SET @id_nouvelle_commande = LAST_INSERT_ID(); INSERT INTO ligne_commande (id_commande, id_produit, quantite, prix_unitaire) VALUES (@id_nouvelle_commande, 3, 2, 29.99); INSERT INTO ligne_commande (id_commande, id_produit, quantite, prix_unitaire) VALUES (@id_nouvelle_commande, 7, 1, 49.99); UPDATE produit SET stock = stock - 2 WHERE id_produit = 3; UPDATE produit SET stock = stock - 1 WHERE id_produit = 7; COMMIT;
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

## Cours - Produits à plus de 100 €
```
SELECT id_produit, nom, prix FROM produit WHERE prix > 100;
```

## Cours - Commandes livrées sans frais de livraison (AND)
```
SELECT * FROM commande_client WHERE statut_commande = 'livrée' AND frais_livraison = 0;
```

## Cours - Commandes livrées du client 1
```
SELECT id_commande FROM commande_client WHERE id_client = 1 AND statut_commande = "livrée";
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

## Cours - LIKE : noms finissant par « son »
```
SELECT * FROM client WHERE nom LIKE '%son';
```

## Cours - LIKE : noms contenant « ar »
```
SELECT * FROM client WHERE nom LIKE '%ar%';
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

## Limiter le nombre de résultats (sans tri, ordre non garanti)
```
SELECT <colonnes> FROM <table> LIMIT <n>;
```

## Top N (tri + LIMIT)
```
SELECT <colonnes> FROM <table> ORDER BY <colonne> DESC LIMIT <n>;
```

## Supprimer les doublons
```
SELECT DISTINCT <colonne> FROM <table>;
```

## Cours - DISTINCT + WHERE + ORDER BY + LIMIT
```
SELECT DISTINCT id_client FROM commande_client WHERE statut_commande = 'livrée' ORDER BY id_client LIMIT 5;
```

## Compter les lignes
```
SELECT COUNT(*) FROM <table>;
```

## Compter les valeurs non NULL d'une colonne
```
SELECT COUNT(<colonne>) FROM <table>;
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

## Cours - Prix moyen par catégorie
```
SELECT id_categorie, AVG(prix) FROM produit GROUP BY id_categorie;
```

## Cours - Nombre de commandes par client et par statut
```
SELECT id_client, statut_commande, COUNT(*) FROM commande_client GROUP BY id_client, statut_commande;
```

## Filtrer les groupes avec HAVING
```
SELECT <colonne_groupe>, COUNT(*) FROM <table> GROUP BY <colonne_groupe> HAVING COUNT(*) > <n>;
```

## Cours - Top 5 clients par nombre de commandes (sans jointure)
```
SELECT id_client, COUNT(*) AS nb_commandes FROM commande_client GROUP BY id_client ORDER BY nb_commandes DESC LIMIT 5;
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

## Cours - Joindre client et commande (colonnes préfixées par la table)
```
SELECT client.nom, client.prenom, commande_client.id_commande FROM client JOIN commande_client ON client.id_client = commande_client.id_client;
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

## Cours - Fonction dans un WHERE : partie entière du prix > 100
```
SELECT nom, description, prix FROM produit WHERE TRUNCATE(prix,0) > 100 ORDER BY prix LIMIT 4;
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

## Cours - Recherche insensible à la casse
```
SELECT * FROM client WHERE LOWER(nom) = 'martin';
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

## Cours - CONCAT_WS : nom complet + contact
```
SELECT id_client, CONCAT_WS(' ', prenom, nom) AS nom_complet, CONCAT_WS(' | ', email, telephone) AS contact FROM client LIMIT 5;
```

## Remplacer l'affichage des NULL
```
SELECT COALESCE(<colonne>, '<valeur_si_null>') FROM <table>;
```

## Cours - Afficher « Non renseignée » à la place des NULL
```
SELECT nom, COALESCE(description, 'Non renseignée') AS description FROM categorie;
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

## Cours - Nettoyer un numéro de téléphone (supprimer les espaces)
```
SELECT REPLACE("06 03 04 XX XX", ' ', '') AS telephone_nettoye;
```

## Date et heure actuelles
```
SELECT NOW(), CURDATE(), CURTIME();
```

## Filtrer sur une période (DATETIME)
```
SELECT * FROM <table> WHERE <colonne_date> >= '<YYYY-MM-DD>' AND <colonne_date> < '<YYYY-MM-DD>';
```

## Cours - Commandes de janvier 2025 (>= et < plutôt que BETWEEN)
```
SELECT * FROM commande WHERE date_commande >= '2025-01-01' AND date_commande < '2025-02-01';
```

## Extraire année / mois / jour
```
SELECT YEAR(<colonne_date>), MONTH(<colonne_date>), DAY(<colonne_date>) FROM <table>;
```

## Cours - Nombre de commandes par année
```
SELECT COUNT(date_commande), YEAR(date_commande) AS annee FROM commande_client GROUP BY annee;
```

## Formater une date
```
SELECT DATE_FORMAT(<colonne_date>, '%d/%m/%Y') AS date_fr FROM <table>;
```

## Ajouter un intervalle à une date
```
SELECT DATE_ADD(<colonne_date>, INTERVAL <n> DAY) FROM <table>;
```

## Cours - Date de livraison estimée (commande + 7 jours)
```
SELECT id_commande, date_commande, DATE_ADD(date_commande, INTERVAL 7 DAY) AS date_livraison FROM commande_client;
```

## Retirer un intervalle à une date
```
SELECT DATE_SUB(CURDATE(), INTERVAL <n> YEAR);
```

## Cours - Commandes de la dernière année
```
SELECT count(id_commande) FROM commande_client WHERE date_commande >= DATE_SUB(CURDATE(), INTERVAL 1 YEAR);
```

## Écart en jours entre deux dates
```
SELECT DATEDIFF(NOW(), <colonne_date>) AS nb_jours FROM <table>;
```

## Cours - Les 3 clients inscrits depuis le plus longtemps
```
SELECT nom, prenom, DATEDIFF(NOW(), date_inscription) AS nb_jours FROM client ORDER BY nb_jours DESC LIMIT 3;
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

## Injection SQL - requête vulnérable (saisie collée dans la requête)
```
SELECT * FROM client WHERE email = '$email';
```

## Injection SQL - requête injectée (condition toujours vraie)
```
SELECT * FROM client WHERE email = '' OR 1=1;
```

## Requête préparée (SQL)
```
SELECT * FROM client WHERE email = ?;
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

## Cours - Index sur l'email des clients
```
CREATE INDEX idx_client_email ON client(email);
```

## Créer une vue
```
CREATE VIEW <nom_vue> AS SELECT <colonnes> FROM <table>;
```

## Cours - Vue commandes + clients
```
CREATE VIEW vue_commandes_clients AS SELECT c.nom, c.prenom, cc.id_commande, cc.date_commande, cc.statut_commande FROM client AS c JOIN commande_client AS cc ON c.id_client = cc.id_client;
```

## Créer un trigger (mise à jour auto d'une date de modification)
```
CREATE TRIGGER maj_date_modification BEFORE UPDATE ON commande_client FOR EACH ROW SET NEW.date_modification = NOW();
```