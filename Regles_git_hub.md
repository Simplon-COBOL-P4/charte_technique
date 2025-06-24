[Retour](.)
# Git / hub
## Général
#### Protection de Push/Merge
Ne je jamais push/merge sur la branche main (normalement vous n'avez pas les permissions, mais on sait jamais).
#### Branches
Toujours créer une branche par ticket, pour ne pas empiéter sur le travail des autres, et éviter les merge conflicts. Une branche s'appelle CP-OXX-NOM-DU-TICKET, example : CP-010-hash-mdp.
#### Pull requests.
Une fois le travail terminé, faire une pull request sur github.
## Commits
[type] Message clair en français (au présent, max 80 caractères):

Nouveau code, nouvelle fonctionnalité <br>
`[ajout] Lecture du fichier client`

Modification d’un code existant <br>
`[modif] Correction boucle de tri`

fix		Correction de bug	<br>
`[fix] Gestion erreur division`

Ajout ou changement dans la documentation <br>
`[doc] Ajout d’un exemple dans README`

Suppression de code inutile ou mise au propre <br>
`[nettoyage] Suppression de variables inutiles`

Ajout/modif de tests <br>
`[test] Ajout de test sur module calcul`

Toujours utiliser un type entre crochets. <br>
Écrire le message en français, clair, au présent. <br>
Un seul sujet par commit. <br>
Pas de message comme "update", "changement", "truc", "fix again" <br>
Si 80 caractères n'est pas suffisant pour votre commit, vous devriez sûrement commit plus souvent.

Exemple : <br>
git commit -m "[type] Message clair en français"