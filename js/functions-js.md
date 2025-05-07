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

---

## 📦 Variables locales

### 📍 Définition :

Une variable locale est une variable déclarée à l’intérieur d’une fonction avec let, const ou var.

🛡️ Elle est invisible et inaccessible en dehors de cette fonction.

### 🔒 Exemple :

```js
function showMessage() {
  let message = "Hello, I'm JavaScript!"; // 🎯 Variable locale
  alert(message); // ✅ Affiche : Hello, I'm JavaScript!
}

showMessage();

alert(message); // ❌ Erreur ! "message" n'existe pas ici car local a la fonction
```

### ***🔎 Pourquoi ?***

Quand une variable est déclarée dans une fonction, elle est stockée dans une mémoire temporaire qui disparaît dès que la fonction a fini de s'exécuter.
On dit qu'elle a une portée locale (scope local).

### 🧠 Résumé :

|📌 Où ?|👀 Visible ?|
|---|---|
|À l'intérieur de la fonction|✅ Oui|
|À l’extérieur de la fonction|❌ Non (Erreur !)|

---

## 🌍 Variables externes

🔓 Une fonction peut accéder à des variables déclarées à l’extérieur d’elle-même !

### 🔎 Exemple simple :

```js
let userName = 'John';

function showMessage() {
  let message = 'Hello, ' + userName;
  alert(message);
}

showMessage(); // ✅ Affiche : Hello, John
```

➡️ La fonction utilise la variable userName déclarée à l’extérieur, car elle n’est pas redéclarée à l’intérieur.

---

## 🕶️ Masquage de variable (variable shadowing)

**🔁 Si une variable locale a le même nom qu'une variable externe, la locale l’emporte !**

***👉 La variable interne “éclipse” ou “cache” la variable externe.***

### 👀 Exemple :

```js
let userName = 'John';

function showMessage() {
  let userName = "Bob"; // 🛑 Variable locale avec le même nom

  let message = 'Hello, ' + userName;
  alert(message); // ✅ Affiche : Hello, Bob
}

showMessage();

alert(userName); // ✅ Affiche : John (la variable globale reste inchangée)
```
### 🔍 Explication :

- 📦 let userName = "Bob" est locale à la fonction.

- Elle masque la variable externe userName = 'John' pendant l’exécution de la fonction.

- En dehors de la fonction, c’est toujours la variable globale qui est utilisée.


### 🧠 Résumé :

|📌 Situation|🧠 Ce qui se passe|
|----|----|
|Même nom en interne et en externe|⚠️ La variable locale est prioritaire|
|La variable externe est ignorée|🚫 Pas utilisée dans la fonction|
|La variable globale n'est pas modifiée|✅ Reste intacte|

---

## 🌐 Variables globales

### ***📍 Définition :***

Une variable globale est une variable déclarée en dehors de toute fonction.
Elle est visible partout dans le code, même à l’intérieur des fonctions (sauf si une variable locale la masque).


### ✅ Bonnes pratiques :

**🔒 Évite d’utiliser trop de variables globales !**

**✔️ Elles peuvent être modifiées depuis n’importe où, ce qui rend le code plus difficile à maintenir et à déboguer.**

### 💡 Dans le code moderne :

- On utilise surtout des variables locales

- Les globales ne servent qu’à stocker des infos partagées dans tout le programme (ex. : configuration, état utilisateur…)

---
