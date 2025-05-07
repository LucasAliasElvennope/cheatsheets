# 🧩 Fonctions

## 🔄 Pourquoi utiliser des fonctions ?

Très souvent, on doit répéter une action à plusieurs endroits dans notre script.

### 📌 Exemples :

- Afficher un message quand un visiteur se connecte

- Afficher un message quand un visiteur se déconnecte

- Et peut-être à d'autres moments aussi...

## ***👉 Au lieu de répéter le même code plusieurs fois, on crée une fonction !***

## 🛠️ C’est quoi une fonction ?

Une fonction est un bloc de code qui effectue une tâche précise.
On peut l’appeler (utiliser) autant de fois qu’on veut, sans recopier le code !

🧠 Les fonctions sont l’un des éléments clés d’un programme : elles le rendent modulaire, réutilisable et plus facile à lire.

### 🔔 On connaît déjà des fonctions toutes faites :

- alert(message) ➜ Affiche une alerte

- prompt(message, default) ➜ Demande une saisie à l’utilisateur

- confirm(question) ➜ Pose une question avec "OK" ou "Annuler"

**✅ Ces fonctions sont intégrées dans JavaScript (on les appelle des fonctions natives ou intégrées).**

---


## 🧾 Déclaration de `fonction`

### ✨ Comment créer une fonction ?

On utilise le mot-clé function, suivi :

- Du nom de la fonction 🏷️

- De parenthèses () (avec ou sans paramètres)

- Et de { accolades } pour délimiter le corps de la fonction (le code à exécuter)

## 🧱 Structure :

```js
function nomDeLaFonction(param1, param2, ..., paramN) {
  // 💬 Code à exécuter (corps de la fonction)
}
```

### 👀 Exemple simple :

```js
function showMessage() {
  alert('Hello everyone!');
}
```

➡️ Ici, showMessage est le nom de la fonction. Elle ne prend aucun paramètre et affiche une alerte.

### ***🧑‍💻 Comment l'utiliser ?***

Il suffit d’appeler la fonction par son nom, suivi de () :

```js
showMessage();
showMessage();
```

👉 Ce code va afficher deux fois une alerte avec "Hello everyone!", car on appelle la fonction deux fois ✅

### 🎯 À quoi ça sert ?

💡 L’un des grands avantages des fonctions est d’éviter la répétition de code (DRY = Don't Repeat Yourself).

**✔️ Si on veut changer le message plus tard, il suffit de le modifier à un seul endroit : dans la fonction.**
