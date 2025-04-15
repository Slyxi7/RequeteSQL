### 1 - Quels sont les tickets qui comportent l’article d’ID 500, afficher le numéro de ticket uniquement ?

- SELECT ANNEE, NUMERO_TICKET FROM vendre WHERE ID_ARTICLE = 500
---
### 2 - Afficher les tickets du 15/01/2017.

- SELECT * FROM vente WHERE DATE_VENTE = 20170115 
---
### 3 - Afficher les tickets émis du 15/01/2017 au 17/01/2017.

- SELECT * FROM vente WHERE DATE_VENTE BETWEEN 20170115 AND 20170117
---
### 4 - Editer la liste des articles apparaissant sur un ticket à au moins 95 exemplaires.

- SELECT DISTINCT a.NOM_ARTICLE FROM vendre v JOIN article a ON v.ID_ARTICLE = a.ID_ARTICLE WHERE v.QUANTITE >= 95
---
### 5 - Quelles sont les tickets émis au mois de mars 2017.

- SELECT * FROM vente WHERE DATE_VENTE BETWEEN 20170301 AND 20170331
---
### 6 - Quelles sont les tickets émis au deuxième trimestre 2017 ?

- SELECT * FROM vente WHERE ANNEE = 2017 AND MONTH(DATE_VENTE) BETWEEN 4 AND 6

---
### 7 - Quelles sont les tickets émis au mois de mars et juillet 2017 ?

- SELECT * FROM vente WHERE YEAR(DATE_VENTE) = 2017 AND MONTH(DATE_VENTE) IN (3, 7)
---
### 8 - Afficher la liste des bières classée par couleur. (Afficher id et nom de bière, nom de la couleur)

- SELECT a.id_article, a.nom_article, c.nom_couleur FROM article a JOIN couleur c ON a.id_couleur = c.id_couleur ORDER BY c.nom_couleur
---
### 9 - Afficher la liste des bières n’ayant pas de couleur. (Afficher l’id et le nom)

- SELECT ID_ARTICLE, NOM_ARTICLE FROM article WHERE ID_COULEUR IS NULL
---
### 10 - Donnez la liste des bières de même couleur et de même type que la bière ayant l’id 142. (affichez le code et le nom de la bière, le nom de la couleur et le nom du type)

- 
---
### 11 - Lister pour chaque ticket la quantité totale d’articles vendus. (Classer par quantité décroissante)

- SELECT ANNEE, NUMERO_TICKET, SUM(QUANTITE) AS TOTAL_QUANTITE FROM vendre GROUP BY ANNEE, NUMERO_TICKET ORDER BY TOTAL_QUANTITE DESC
---
### 12  Lister chaque ticket pour lequel la quantité totale d’articles vendus est inférieure à 50. (Classer par quantité croissante)

- SELECT ANNEE, NUMERO_TICKET, SUM(QUANTITE) AS TOTAL_QUANTITE FROM vendre GROUP BY ANNEE, NUMERO_TICKET HAVING TOTAL_QUANTITE < 50 ORDER BY TOTAL_QUANTITE ASC
---
### 13  Lister chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500.(Classer par quantité décroissante)

- SELECT ANNEE, NUMERO_TICKET, SUM(QUANTITE) AS TOTAL_QUANTITE FROM vendre GROUP BY ANNEE, NUMERO_TICKET HAVING TOTAL_QUANTITE > 500 ORDER BY TOTAL_QUANTITE DESC
---
### 14  Lister chaque ticket pour lequel la quantité totale d’articles vendus est supérieure à 500. On exclura du total, les ventes ayant une quantité supérieure à 50 (classer par quantité décroissante)

- SELECT ANNEE, NUMERO_TICKET, SUM(QUANTITE) AS TOTAL_QUANTITE FROM vendre WHERE QUANTITE <= 50 GROUP BY ANNEE, NUMERO_TICKET HAVING TOTAL_QUANTITE > 500 ORDER BY TOTAL_QUANTITE DESC
---
### 15  Lister les bières de type ‘Trappiste’. (id, nom de la bière, volume et titrage)

- SELECT a.ID_ARTICLE, a.NOM_ARTICLE, a.VOLUME, a.TITRAGE FROM article a JOIN type t ON a.ID_TYPE = t.ID_TYPE WHERE t.NOM_TYPE = 'Trappiste';
---
### 16  Lister les marques de bières du continent ‘Afrique’

- SELECT DISTINCT m.NOM_MARQUE FROM marque m JOIN pays p ON m.ID_PAYS = p.ID_PAYS JOIN continent c ON p.ID_CONTINENT = c.ID_CONTINENT WHERE c.NOM_CONTINENT = 'Afrique'
---
### 17  Lister les bières du continent ‘Afrique’

- SELECT a.ID_ARTICLE, a.NOM_ARTICLE, a.VOLUME FROM article a JOIN marque m ON a.ID_MARQUE = m.ID_MARQUE JOIN pays p ON m.ID_PAYS = p.ID_PAYS JOIN continent c ON p.ID_CONTINENT = c.ID_CONTINENT WHERE c.NOM_CONTINENT = 'Afrique'
---
### 18 Lister les tickets (année, numéro de ticket, montant total payé). En sachant que : Le taux de TVA est fixé à 20%.

- 
---
### 19 Donner le C.A. par année.

- 
---
### 20 Lister les quantités vendues de chaque article pour l’année 2017.

- SELECT a.ID_ARTICLE, a.NOM_ARTICLE, SUM(v.QUANTITE) AS QUANTITE_VENDUE FROM vendre v JOIN article a ON v.ID_ARTICLE = a.ID_ARTICLE WHERE v.ANNEE = 2017 GROUP BY a.ID_ARTICLE, a.NOM_ARTICLE ORDER BY QUANTITE_VENDUE DESC
---
### 21 Lister les quantités vendues de chaque article pour les années 2014,2015, 2016, 2017.

- SELECT v.ANNEE, a.ID_ARTICLE, a.NOM_ARTICLE, SUM(v.QUANTITE) AS QUANTITE_VENDUE FROM vendre v JOIN article a ON v.ID_ARTICLE = a.ID_ARTICLE WHERE v.ANNEE IN (2014, 2015, 2016, 2017)GROUP BY v.ANNEE, a.ID_ARTICLE, a.NOM_ARTICLE ORDER BY v.ANNEE, QUANTITE_VENDUE DESC
---
### 22 Lister les articles qui n’ont fait l’objet d’aucune vente en 2015.

- 
---
