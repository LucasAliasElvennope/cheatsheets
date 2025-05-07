# 📦 Découvrir les Objets en JavaScript

## 🔑 1. Principe clé / valeur

Un objet est une collection de paires clé/valeur.
Chaque clé (aussi appelée propriété) est une chaîne et est liée à une valeur.

### 🧱 Syntaxe de base :

```js
let user = {
  name: "Alice",   // clé : "name", valeur : "Alice"
  age: 25,
  isAdmin: true
};
```

## 🔍 On accède à une valeur avec :

```js
alert(user.name);      // Alice
alert(user["age"]);    // 25
```

## 🧍‍♂️ 2. Objet vs Variable

📦 Objet = conteneur de plusieurs données regroupées sous forme de clé/valeur.

### 🔹 Variable simple :

```js
let name = "Bob";
```

### 🔸 Objet :

```js
let person = {
  name: "Bob",
  age: 30
};
```

➡️ Une variable stocke une seule valeur,
➡️ Un objet stocke plusieurs valeurs sous forme organisée 🗂️.

## 🔁 3. Itérer dans un objet (boucle for..in)

Utilise for..in pour parcourir toutes les clés d’un objet :

```js
let user = {
  name: "Léo",
  age: 22,
  isAdmin: false
};

for (let key in user) {
  alert(key);         // 🔑 Affiche la clé
  alert(user[key]);   // 📦 Affiche la valeur correspondante
}
```

## 🧬 4. Copier un objet (Cloner)

### ❌ Si tu fais ça :

```js
let user = { name: "Léa" };
let copy = user;
```

➡️ Les deux variables pointent vers le même objet (modification mutuelle).

### ✅ Pour copier sans lien, utilise Object.assign() :

```js
let user = { name: "Léa", age: 25 };
let copy = Object.assign({}, user);
```

🪄 Ou avec le spread operator ... (méthode moderne) :

```js
let copy = { ...user };
```

⚠️ Ces méthodes font une "copie superficielle" (shallow copy) :
Si l'objet contient d'autres objets imbriqués, ils ne sont pas clonés en profondeur.