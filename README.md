# Test-WL

## Synchronisation avec GitHub

Si la synchronisation automatique échoue dans Replit, suivez les étapes ci-dessous pour connecter
manuellement ce dépôt à un dépôt GitHub :

1. Récupérez l’URL HTTPS de votre dépôt GitHub. Elle ressemble à
   `https://github.com/<utilisateur>/<nom-du-depot>.git`.
2. Dans le terminal Replit, assurez-vous d’être dans ce dossier puis exécutez :
   ```bash
   git remote add origin <URL-du-depot>
   ```
   (Remplacez `<URL-du-depot>` par l’URL copiée à l’étape précédente.)
3. Vérifiez que le remote est bien configuré avec `git remote -v`.
4. Commitez vos changements locaux :
   ```bash
   git add .
   git commit -m "Votre message de commit"
   ```
5. Poussez vos changements vers GitHub :
   ```bash
   git push -u origin work
   ```
   (Remplacez `work` par le nom de votre branche si nécessaire.)

Si l’étape 2 renvoie une erreur parce qu’un remote existe déjà, supprimez-le d’abord
avec `git remote remove origin` puis relancez la commande `git remote add …`.
