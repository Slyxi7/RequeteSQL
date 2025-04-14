### Requête 1 : Sélectionner toutes les colonnes de la table SERV.

SELECT * FROM serv;

### Requête 2 : Sélectionner d’une autre manière ces colonnes.

SELECT noserv, service, ville
FROM serv;

### Requête 3 : Sélectionner les colonnes SERVICE et NOSERV de la table SERV. 

SELECT service, noserv
FROM serv;

### Requête 4 : Sélectionner toutes les colonnes de la table EMP.

SELECT * FROM emp

### Requête 5 : Sélectionner les emplois de la table EMP.

SELECT emploi FROM emp

### Requête 6 : Sélectionner les différents emplois de la table EMP.

SELECT DISTINCT emploi FROM emp

### Requête 7 : Sélectionner les employés du service N°3.

SELECT nom, prenom FROM emp WHERE noserv = 3

### Requête 8 : Sélectionner les noms, prénoms, numéro d’employé, numéro de service de tous les techniciens.

SELECT nom, prenom, noemp, noserv FROM emp WHERE emploi = 'TECHNICIEN'

### Requête 9 : Sélectionner les noms, numéros de service de tous les services dont le numéro est supérieur à 2.

SELECT nom, prenom, noserv FROM emp WHERE noserv > 2

### Requête 10 : 10 : Sélectionner les noms, numéros de service de tous les services dont le numéro est inférieur ou égal à 2.

SELECT nom, prenom, noserv FROM emp WHERE noserv <= 2

### Requete 11 : Sélectionner les employés dont la commission est inférieure au salaire.

SELECT nom FROM emp WHERE comm < sal

### Requête 12 : Sélectionner les employés qui ne touchent jamais de commission.

SELECT nom FROM emp WHERE comm is null

