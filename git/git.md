# Git

## Configuration de Git

---
git config --global user.name "TonPseudoGitHub"

git config --global user.email "TonEmail@example.com"

git config --global core.editor "vim"  # (ou nano, code, etc.)

git config --list  # Vérifier la configuration actuelle

---

## Initialiser un projet Git

git init  # Initialise un dépôt Git local

git clone <URL>  # Clone un dépôt distant

---

## Suivi et validation des fichiers

git status  # Vérifier l'état des fichiers

git add <fichier>  # Ajouter un fichier au suivi

git add .  # Ajouter tous les fichiers modifiés

git commit -m "Message du commit"  # Enregistrer les modifications

git commit --amend  # Modifier le dernier commit (avant push)

---

## Gestion des branches

git branch  # Lister les branches locales

git branch -a  # Lister toutes les branches (locales + distantes)

git branch <nom_de_la_branche>  # Créer une nouvelle branche

git checkout <nom_de_la_branche>  # Changer de branche

git switch <nom_de_la_branche>  # Alternative à checkout

git checkout -b <nom_de_la_branche>  # Créer et passer sur une nouvelle branche

git switch -c <nom_de_la_branche>  # Alternative moderne

git branch -d <nom_de_la_branche>  # Supprimer une branche locale

git push origin --delete <nom_de_la_branche>  # Supprimer une branche distante

---

## Fusion et Rebase

git merge <branche_source>  # Fusionner une branche dans l'actuell

git rebase <branche_source>  # Rebaser la branche actuelle sur une autre

---

## Remonter et récupérer du code sur GitHub

git remote -v  # Vérifier les dépôts distants

git remote add origin <URL>  # Ajouter un dépôt distant

git push -u origin <branche>  # Pousser une branche sur GitHub

git pull origin <branche>  # Récupérer les modifications distantes

git fetch  # Récupérer les branches et mises à jour distantes 

---

# Travailler avec GitHub (Pull Requests & Forks)

git fork  # À faire sur GitHub pour copier un repo

git remote add upstream <URL>  # Lier un repo forké au repo original

git fetch upstream  # Récupérer les mises à jour du repo original

git merge upstream/main  # Fusionner les mises à jour dans ton fork

git push origin <branche>  # Pousser tes modifications

git pull-request  # Créer une Pull Request (via GitHub CLI)

---

| Action | Commande |
|:--------|---------:|
| Initialiser Git | git init |
| Ajouter un fichier | git add <fichier> |
| Faire un commit | git commit -m "message" |
| Créer une branche | git branch <nom> |
| Changer de branche | git checkout <nom> ou git switch <nom> |
| Fusionner des branches | git merge <branche> |
| Récupérer un repo | git clone <URL> |
| Pousser les modifications | git push origin <branche> |
| Récupérer les modifications | git pull origin <branche> |
| Afficher l'historique | git log --oneline --graph |





