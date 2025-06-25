[Retour](.)
# COBOL
## Nomenclature
### Général
Jamais d'underscore `_`, que des tirets `-`<br>
Chaque mot, ou identifiant est séparé par un tiret
### Les trigrammes
Chaque mot utilisé dans un nom de variable, doit être abrégé en 3 lettres, pour former un trigramme.<br>
Il faut être cohérent dans l'utilisation des trigrammes, essayer de garder les même trigrammes pour les mêmes mots.<br>
Il est demandé que tous les trigrammes soient documentés en haut de chaque programme, dans l'entête <br>
Exemple : <br>
Variable NOMBRE-VENTE-CLIENT dans la WORKING-STORAGE.<br>
```
On utilise WS car c'est dans la WORKING-STORAGE.
```
```
NOMBRE -> NBR (Le trigramme exact est un choix, regarder les autres codes pour voir comment les autres ont fait peut-être une option)
VENTE  -> VNT
CLIENT -> CLT
```
La variable sera donc `WS-NBR-VNT-CLT`.<br>
Et on aura, au niveau de l'entête du programme, une référence à tous les trigrammes et les mots qui leur correspond :<br>
`* NOMBRE=NBR; VENTE=VNT; CLIENT=CLT;.`<br>
Il pourrait dans le futur y avoir un outil qui permettrait une gestion plus simple et commune au projet des trigrammes, mais la solution n'existe pas encore.
### Noms des programmes
Le nom d'un programme ne doit jamais dépasser **8 lettres**, et doit être écrit en **minuscule**. **Tirets interdits**, seules les **lettres** sont **autorisées**. Écrire aussi en trigramme, et penser à documenter ceux-ci aussi dans l'entête.<br>
Le nom d'un Copybook doit toujours finir par ".cpy".
### Noms des variables
```
WORKING STORAGE SECTION -> WS
LINKAGE SECTION         -> LK
FILE SECTION            -> F
SCREEN SECTION          -> S
```
### Les paragraphes
Un paragraphe doit toujours suivre la nomenclature suivante : Sans oublier les trigrammes, et leur documentation dans l'entête. <br>
```
 0100-CRE-USR-DEB.
 0100-CRE-USR-FIN.
```
Un appel de paragraphe est toujours fait de la manière suivante, identé de cette manière :
```
 PERFORM 0100-CRE-USR-DEB
    THRU 0100-CRE-USR-FIN.
```
## Structure
Entête avant le programme qui explique ce qu'il fait est obligatoire, il contiendra aussi les informations des trigrammes.

TOUT code doit être commenté, pas besoin de commenter un `OPEN INPUT F-INPUT.`, car c'est très explicite, mais dès qu'une logique peut nécessiter une explication, on la donne, expliquer l'utilité des variables, des fd, et surtout des paragraphes est obligatoire.

AUTHOR et DATE-WRITTEN (format `DATE-WRITTEN. JJ-MM-YYYY (fr).`) obligatoires.

Jamais de code dans la `PROCEDURE DIVISION.`, tout code doit être écrit dans les paragraphes, à part l'appel des paragraphes eux-mêmes.

`WS-DUMMY PIC .. VALUE` doit être utilisé avec parcimonie, dans de nombreux cas, il est plus clair d'initialiser une variable au moment où on s'en sert, je fais particulièrement référence aux indices (index au pluriel)

L'utilisation de `LOCAL SECTION`. est interdit.

Le code de la `PROCEDURE DIVISION.` DOIT commencer à la colonne 12, et non à la 8.

L'identation doit être propre, et faite à chaque scope, l'indentation est FIXÉE à 4 colonnes. Si la fin des colonnes est atteinte, il est probable que plus de paragraphes auraient pu être créés.

`PIC X(2)` est interdit, `PIC X(02)` est attendu.

Tous les PIC doivent être alignés, dans la limite du raisonnable. Apprendre des raccourcis VSCode peut-être utile.

Les niveaux d'accès des variables doivent être incrémentés par 5 à l'exception du premier : 01, 05, 10 .. etc.

Toutes les variables indépendantes (Index etc) doivent être des variables 77.

Les flags (88) doivent être utilisés dès que nécessaire, se renseigner sur cette pratique peut être intéressant.

Les `MOVE .. TO` doivent être alignés.

Toutes les `SCREEN SECTION` doivent être faites de sorte à fonctionner sur le format terminal de base, soit 80 colonnes par 24 lignes.
## Tests
### FICHIERS ENTRÉE-SORTIE : 
```
Tester avec fichier / donnée vide
Tester avec fichier malformés
```
### SCREEN SECTION :
```
Tester avec entrée utilisateur vide
Tester avec mauvais type d'entrée
```
###	SQL :
```
Tester avec tables vides / manquantes
```