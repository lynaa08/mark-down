# TP Oracle – Dictionnaire de données

## Introduction

Oracle dispose d’une structure centralisée appelée **dictionnaire de données** contenant la description de tous les objets gérés par le SGBD (tables, vues, utilisateurs, index, etc.).

Ce dictionnaire est une **méta‑base**, organisée comme une base de données et accessible via SQL. Pour des raisons d’intégrité, seules certaines vues sont consultables par les utilisateurs (l’administrateur `SYS` étant le seul à pouvoir modifier les tables internes).

Les informations du dictionnaire sont accessibles à travers des **vues**, réparties en quatre grandes catégories :

- `USER_*` : objets appartenant à l’utilisateur
- `ALL_*` : objets accessibles à l’utilisateur
- `DBA_*` : vues réservées à l’administrateur
- `V$*` : vues liées aux performances

Dans ce TP, nous nous intéressons principalement aux vues **USER** et **ALL**.

---

## Vues du dictionnaire de données (USER_*)

| Nom de la vue | Synonyme | Description |
|--------------|----------|-------------|
| DICTIONARY | DICT | Liste toutes les vues du dictionnaire avec leur description |
| USER_TABLES | TABS | Tables de l’utilisateur : nom, tablespace, stockage, statistiques |
| USER_TAB_COLUMNS | COLS | Colonnes des tables : nom, type, longueur, nullabilité |
| USER_VIEWS | – | Vues de l’utilisateur : nom et requête SQL |
| USER_INDEXES | IND | Index : nom, table indexée, unicité, stockage |
| USER_IND_COLUMNS | – | Colonnes des index : nom, table, colonne, position |
| USER_CLUSTERS | CLU | Clusters de l’utilisateur |
| USER_OBJECTS | OBJ | Tous les objets : tables, vues, index, procédures, séquences |
| USER_SEQUENCES | SEQ | Séquences : min, max, incrément, cycle, cache |
| USER_SYNONYMS | SYN | Synonymes : nom, table, propriétaire, dblink |
| USER_USERS | – | Informations générales de l’utilisateur |
| USER_CONSTRAINTS | – | Contraintes : nom, type, table, statut |
| USER_DB_LINKS | – | Liens vers bases distantes |
| USER_TAB_PRIVS | – | Privilèges accordés ou reçus |
| USER_EXTENTS | – | Informations de stockage des objets |
| USER_TS_QUOTAS | – | Quotas d’écriture par tablespace |

---

## Questions

### Connexion

> Connectez‑vous (les tables du TP1 doivent être créées).

---

### Partie 1 : Dictionnaire Oracle

1. Se connecter en tant que **SYSTEM**.
   - Lister le catalogue `DICT`
   - Combien d’instances contient‑il ?
   - Donner sa structure

2. Donner le rôle et la structure des vues suivantes :
   - `ALL_TAB_COLUMNS`
   - `USER_USERS`
   - `ALL_CONSTRAINTS`
   - `USER_TAB_PRIVS`

3. Trouver le nom de l’utilisateur avec lequel vous êtes connecté.

4. Comparer la structure et le contenu de :
   - `ALL_TAB_COLUMNS`
   - `USER_TAB_COLUMNS`

5. Vérifier que les tables du **TP1** ont été réellement créées.
   - Donner toutes les informations concernant ces tables.

6. Lister :
   - Les tables de l’utilisateur `SYSTEM`
   - Les tables de votre utilisateur

7. Donner la description des attributs de **deux de vos tables** (en exploitant `USER_TAB_COLUMNS`).

8. Comment vérifier l’existence d’une **clé étrangère** entre deux tables ?

9. Donner toutes les contraintes créées lors du **TP1** ainsi que leurs caractéristiques (à l’aide de `USER_CONSTRAINTS`).

10. Retrouver toutes les informations nécessaires pour **recréer une table**.

11. Trouver tous les privilèges accordés à l’utilisateur **GestionTP2**.

12. Trouver les rôles attribués à l’utilisateur **GererTP2**.

13. Lister tous les objets appartenant à **GestionTP2**.

14. Comment un administrateur peut‑il trouver le **propriétaire d’une table** ?

15. Donner la **taille en Ko** d’une table.

16. Vérifier l’effet de chaque commande de **définition de données (DDL)** du TP1 sur le dictionnaire.

---

## Fin du TP

