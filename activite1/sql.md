# Activit�: Recherchez des donn�es � l'aide de requ�tes SQL

## Objectifs

Le but de cette activit� est de r�diger des requ�tes sur une base de donn�es afin de r�pondre � des questions.
La base de donn�es mod�lise une entreprise, dans laquelle des personnes sont employ�es dans diff�rents d�partements.

## Contexte

Elle contient 6 tables :
 - *employees* : les employ�s
 - *titles* : le titre sous lequel un employ� est embauch�
 - *salaries* : les salaires des employ�s
 - *departements* : les d�partements de l'entreprise
 - *dept_manager* : les managers (chefs) de d�partements
 - *dept_emp* : les employ�s associ�s � un d�partement donn�

Ces tables sont r�sum�es dans ce sch�ma :

![Sch�ma de la base de donn�es](employees-schema.png)

## Consigne

Vous acc�derez � la base de donn�es via cette console interactive.

Il est conseill� de garder une copie des requ�tes que vous r�digez sur votre ordinateur, car la m�moire de la console interactive se r�initialise si la page web est rafra�chie.

Pour chaque question, vous fournirez la requ�te SQL vous ayant permis d'obtenir le r�sultat, ainsi qu'une capture d'�cran de la table renvoy�e par votre requ�te. Si le r�sultat d'une requ�te contient beaucoup de ligne, seule une capture d'�cran des premi�res lignes suffit.

## Questions

 1. Affichez toutes les lignes de la table *employees*, en n'affichant que les noms et pr�noms des employ�s.
 2. Afficher tous les employ�s ayant �t� embauch� apr�s le 1er aout 1999 (non compris).
 3. Dans cette base de donn�es, deux tables ont le m�me sch�ma. R�aliser leur union.
 4. Afficher les diff�rents salaires qu'a eu l'employ� dont l'identifiant est **499593** gr�ce � une jointure.
 5. Gr�ce � une jointure, produisez une table indiquant le ou les d�partements dans lesquels a travaill� l'employ� dont l'identifiant est **499902** (la table doit contenir �galement les dates de d�but et de fin d'embauche dans chacun des d�partements). 
 6. En utilisant une agr�gation, trouver combien de personnes ont pour nom de famille "Gewali" (le nom de famille est donn� dans la colonne *last_name* de la table *"employees"*).

 
## R�ponses

### Question 1

Pour afficher les lignes de la table *employees*, on utilise la commande `SELECT` de la facon suivante

```sql
SELECT last_name, first_name FROM employees;
```

### Question 2

```sql
SELECT last_name, first_name, hire_date FROM employees 
WHERE (hire_date > "01-08-1999") 
ORDER BY hire_date DESC;
```

Note: la commande `ORDER BY hire_date DESC` permet d'ordonner les resultats de la requ�te.


### Question 3 (a tester!)

Les deux tables ayant le sch�ma sont les tables: `dept_emp` et `dept_manager`

```sql
SELECT emp_no, dept_no, from_date, to_date FROM dept_emp
UNION
SELECT emp_no, dept_no, from_date, to_date FROM dept_manager;
```

### Question 4

### Question 5

### Question 6