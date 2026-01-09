# Instructions -- Workflow Git & GitHub

Cet exercice est basé sur [ce projet](https://github.com/mathurinm/github-assignment) maintenu par Mathurin Massias.

## 0. Créer un personnal access token 

- Allez sur [ce lien](https://github.com/settings/tokens)

- Cliquez sur **Generate new token** (classic)

- Donnez un nom à ce token (par ex : _cours-git__)

- Cochez l'option **repo**

- Cliquez sur **Generate token**

- Copiez le token dans un endroit sûr (_e.g. Bitwarden, Proton_)

## 1. Forker le dépôt

-   Cliquez sur **Fork** en haut à droite de la page GitHub du projet.

## 2. Cloner votre fork

    git clone VOTRE_URL_DE_FORK

## 3. Vérifier les dépôts distants (remotes)

    git remote -v

Vous devez voir l'URL de votre fork (`origin`).

## 4. Ajouter le dépôt original comme remote upstream

    git remote add upstream https://github.com/thom1100/GitHub_assignement

## 5. Vérifier à nouveau les remotes

    git remote -v

Vous devez maintenant voir **origin** et **upstream**.

## 6. Créer une branche à votre nom

    git branch -c YOURNAME
    git checkout YOURNAME

Vérifier : git status

## 7. Modifier le fichier students.txt

-   Ouvrez le fichier localement.
-   Ajoutez un **X** à la fin de la ligne où apparaît votre nom.

## 8. Ajouter et commit

    git add students.txt
    git commit -m "Update students.txt : Ajout du X à côté de mon nom"

Vérifier : git status

## 9. Pousser votre branche vers votre fork

    git push --set-upstream origin YOURNAME

## 10. Créer une Pull Request

-   Rendez-vous sur :
    [https://github.com/thom1100/GitHub_assignments/pulls](https://github.com/thom1100/GitHub_assignement/pulls)
    
    Créez une PR depuis votre branche vers `main` du repo original.

## 11. En cas de conflits

Il est possible / probable qu'au moment de merger votre branche avec la branche main du repo original, votre version de students.txt ne soit pas à jour avec la version qui est sur le repo upstream (quelqu'un a merge avant vous) : vous aurez donc un conflit.

Pour le résoudre : 

- Mettre à jour votre working directory : git pull upstream main

- Résoudre les conflits : depuis vs code en intégrant les modifications d'upstream dans votre working directory

- Reprendre le même workflow : git add . git commit git push

## 12. Me prévenir

Pour que je puisse merger votre branche.

## 13. Après le merge

Supprimez votre branche

    git switch main
    git branch -D YOURNAME

## 14. Synchroniser votre main

    git pull upstream main

Bravo vous venez de faire votre première Pull Request !
