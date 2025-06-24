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
Le nom d'un programme ne doit jamais dépasser **8 lettres**, et doit être écrit en **minuscule**. **Tirets interdits**, seules les **lettres** sont **autorisées**. Écrire aussi en trigramme, et penser à documenter ceux-ci aussi dans l'entête.
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