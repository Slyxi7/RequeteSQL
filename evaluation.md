### 1 - Quels sont les tickets qui comportent l’article d’ID 500, afficher le numéro de ticket uniquement ?

- SELECT ANNEE, NUMERO_TICKET FROM vendre WHERE ID_ARTICLE = 500

### 2 - Afficher les tickets du 15/01/2017.

- SELECT * FROM vente WHERE DATE_VENTE = 20170115 

### 3 - Afficher les tickets émis du 15/01/2017 au 17/01/2017.

- SELECT * FROM vente WHERE DATE_VENTE BETWEEN 20170115 AND 20170117

### 4 - Editer la liste des articles apparaissant sur un ticket à au moins 95 exemplaires.

- 

### 5 - Quelles sont les tickets émis au mois de mars 2017.

- SELECT * FROM vente WHERE DATE_VENTE BETWEEN 20170301 AND 20170331

### 6 - Quelles sont les tickets émis au deuxième trimestre 2017 ?

- 

### 7 - Quelles sont les tickets émis au mois de mars et juillet 2017 ?

- SELECT * FROM vente WHERE YEAR(DATE_VENTE) = 2017 AND MONTH(DATE_VENTE) IN (3, 7)

### 8 - Afficher la liste des bières classée par couleur. (Afficher id et nom de bière, nom de la couleur)

- 