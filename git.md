## Aide mémoire GIT

### Personnaliser

Définir son identité :
```bash
$ git config --global user.email "email@example.com"
$ git config --global user.name "John Doe"
```

Voir la configuration :
```
git config --list
```

### Créer

Créer un nouveau dépôt local (dans le dossier courant) :
```
$ git init
```

Cloner un dépot existant :
```
$ git clone ssh://user@domain.com/repo.git
```

Créer un fichier « .gitignore » pour OSX:
```
$ curl -s https://www.gitignore.io/api/osx > .gitignore
```

### Modifications locales

Fichiers modifiés dans votre répertoire de travail :
```
$ git status
```

Modifications sur les fichiers suivis :
```
$ git diff
```

Ajouter tous les changements actuelles au prochain commit :
```
$ git add
```

Ajouter tous les changements de toute l’arborescence :
```
$ git add --all
```

Commiter tous les changements locaux des fichiers suivis :
```
$ git commit -a
```

Commiter les modifications en attente :
```
$ git commit -m 'Votre message'
```

Modifier le commit précédent :
```
$ git commit --amend
```

### Historique de Commit

Afficher tous les commits :
```
$ git log
```

Afficher tous les commits (uniquement l’identifiant et le texte) :
```
$ git log --oneline
```

Afficher l’historique d’un utilisateur uniquement :
```
$ git log --author="utilisateur"
```

Afficher l'historiques des modifications pour un fichier uniquement :
```
$ git log -p <fichier>
```

Affiche les changement (en détails) dans le fichier :
```
$ git blame <file>
```

### Branches & Tags

Lister toutes les branches :
```
$ git branch
```

Changer de branche :
```
$ git checkout <votre-branche>
```

Créer une nouvelle branche en se basant sur le HEAD :
```
$ git branch <votre-branche>
```

Créer une nouvelle branche de suivi, basée sur une branche distante :
```
$ git branch --track <nouvelle-branche> <branche-distante>
```

Supprimer une branche :
```
$ git branch -d <votre-branche>
```

Marqué le commit courant avec un tag :
```
$ git tag <non-du-tag>
```


### Merge & Rebase

Fusionner la branche <votre-branche> avec la master :
```
$ git checkout master
$ git merge <votre-branche>
```

#### ⚠️ Attention ⚠️

Jouer avec l’historique est toujours dangereux surtout si vous travaillez à plusieurs !

Mettre à jour votre branche avec le code de la master :
```
$ git checkout <votre-branch>
$ git rebase master
```

Annuler un rebase en cours :
```
$ git rebase --abort
```

Continuer un rebase après avoir résolu des conflits :
```
$ git rebase --continue
```

### Travailler avec un dépots distant

Lister tout les dépôts distants configurés :
```
$ git remote -v
```

Monter les informations d'un dépôt distant :
```
$ git remote show origin
```

Ajouter un nouveau dépôt distant, nommé &lt;remote&gt; :
```
$ git remote add <remote> <url>
```

Synchronise la branche « origin » avec la master. Et indique origin comme dépôt distant par défaut.
```
$ git push -u origin master
```

Télécharger toutes les modifications d'un dépôt distant nommé &lt;remote&gt;, sans les fusionner :
```
$ git fetch <remote>
```

Télécharger les modifications et les fusionner directement dans le HEAD :
```
$ git remote pull <remote> <url>
```

Récupérer toutes les modifications du HEAD dans le dépôt local :
```
$ git pull
$ # ou
$ git pull origin master
```

Publier les modifications locales sur un dépôt distant :
```
$ git push
$ ou
$ git push remote <remote> <branch>
```

Publier les tags :
```
$ git push --tags
```

### Annulation

Annuler le dernier `git add` :
```
$ git reset HEAD
```

Annuler les modifications locales d'un fichier spécifique :
```
$ git checkout HEAD <file>
```

Annuler un commit (création d’un commit avec les modifications inverses)  :
```
$ git revert <commit>
```

Placer le pointeur du HEAD sur un commit précédent.
Conserve toutes les modifications effectuées depuis :
```
$ git reset <commit>
```

⚠️ Annuler toutes les modifications dans le répertoire de travail :
```
$ git reset --hard HEAD
```

⚠️ Placer le pointeur du HEAD sur un commit précédent.
Annule toutes les modifications effectuées depuis :
```
$ git reset --hard <commit>
```
