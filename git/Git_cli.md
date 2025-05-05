# 📌 Commandes GitHub CLI (gh) - Cheat Sheet

## 🚀 1. Authentification et Configuration
🔹 **Se connecter à GitHub**  
```
gh auth login
```
👉 Connecte ton terminal à ton compte GitHub.

🔹 **Vérifier si on est connecté**  
```
gh auth status
```
👉 Vérifie l’état de l’authentification.

🔹 **Se déconnecter de GitHub**  
```
gh auth logout
```
👉 Déconnecte ton compte GitHub.

---

## 📂 2. Gérer les Dépôts GitHub
🔹 **Lister tous tes dépôts**  
```
gh repo list
```
👉 Affiche une liste de tes dépôts GitHub.

🔹 **Créer un nouveau dépôt**  
```
gh repo create mon-projet --public
```
👉 Crée un nouveau dépôt public.

🔹 **Cloner un dépôt existant**  
```
gh repo clone utilisateur/repo
```
👉 Clone un dépôt GitHub localement.

🔹 **Voir les infos d’un dépôt**  
```
gh repo view utilisateur/repo
```
👉 Affiche les détails d’un dépôt.

🔹 **Ouvrir un dépôt dans le navigateur**  
```
gh repo view --web
```
👉 Ouvre le dépôt actuel sur GitHub.com.

---

## 🛠️ 3. Gérer les Issues
🔹 **Lister les issues ouvertes**  
```
gh issue list
```
👉 Affiche la liste des issues non résolues.

🔹 **Créer une nouvelle issue**  
```
gh issue create --title "Bug détecté" --body "Description du problème"
```
👉 Crée une nouvelle issue avec un titre et une description.

🔹 **Voir les détails d’une issue**  
```
gh issue view 123
```
👉 Affiche les détails de l’issue #123.

🔹 **Fermer une issue**  
```
gh issue close 123
```
👉 Ferme l’issue #123.

---

## 🔄 4. Gérer les Pull Requests (PR)
🔹 **Lister les Pull Requests ouvertes**  
```
gh pr list
```
👉 Affiche les Pull Requests actives.

🔹 **Créer une nouvelle Pull Request**  
```
gh pr create --title "Ajout de fonctionnalité" --body "Description de la PR"
```
👉 Propose une modification à fusionner dans le projet.

🔹 **Voir les détails d’une Pull Request**  
```
gh pr view 123
```
👉 Affiche les détails de la PR #123.

🔹 **Tester une Pull Request localement**  
```
gh pr checkout 123
```
👉 Récupère le code de la PR #123 pour le tester.

🔹 **Fusionner une Pull Request avec Squash**  
```
gh pr merge 123 --squash
```
👉 Fusionne la PR #123 en un seul commit.

🔹 **Fusionner une Pull Request avec Rebase**  
```
gh pr merge 123 --rebase
```
👉 Fusionne la PR en appliquant chaque commit un par un.

🔹 **Supprimer une branche après fusion**  
```
gh pr delete 123
```
👉 Supprime la branche de la PR #123.

---

## 🏗️ 5. Finalisation du Profil GitHub
🔹 **Modifier sa bio GitHub**  
```
gh api -X PATCH user -F bio="Développeur passionné par Linux et Git"
```
👉 Met à jour ta bio GitHub sans passer par le site.

🔹 **Ajouter une clé SSH à son compte GitHub**  
```
gh ssh-key add ~/.ssh/id_rsa.pub --title "Mon PC Linux"
```
👉 Ajoute une clé SSH pour éviter de taper son mot de passe.

---

## 🎯 Résumé
✅ **Créer, cloner et gérer ses dépôts** → `gh repo create`, `gh repo clone`  
✅ **Travailler avec les issues** → `gh issue list`, `gh issue create`  
✅ **Gérer les Pull Requests** → `gh pr list`, `gh pr merge`, `gh pr checkout`  
✅ **Finaliser son profil** → Modifier sa bio, ajouter une clé SSH  

---

💡 **GitHub CLI (`gh`) permet de gagner du temps et d’éviter d’ouvrir GitHub !** 🚀