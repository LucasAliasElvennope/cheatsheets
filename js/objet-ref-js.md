# 📦 Références d'objet et copie en JavaScript

## 🧠 1. Les objets sont copiés par référence, pas par valeur

**🔹 Les primitives (string, number, boolean, etc.) sont copiées par **valeur**
**🔹 Les objets (objets, tableaux, fonctions) sont copiés par **référence****

```js
let message = "Hello!";
let phrase = message;
// Deux variables indépendantes ✔️

let user = { name: "John" };
let admin = user;
// Deux variables qui POINTENT vers le MÊME objet ❗
```

### ***💡 Modifier admin modifie aussi user :***

```js
admin.name = "Pete";
alert(user.name); // Pete ✅
```

## 🔍 2. C’est quoi une référence ?

👉 Une variable objet ne contient pas l’objet lui-même, mais une adresse mémoire où l’objet est stocké.
📫 C’est comme une clé d’armoire : plusieurs clés (variables) peuvent ouvrir la même armoire (objet).

## versa 3. Comparaison d’objets

🟢 Deux objets sont égaux (==, ===) seulement s’ils pointent vers le même objet :

```js
let a = {};
let b = a;
alert(a === b); // true ✅
```

🔴 Même contenu ≠ égalité :

```js
let a = {};
let b = {};
alert(a === b); // false ❌
```

## 🔐 4. Les objets const peuvent être modifiés

```js
const user = { name: "John" };
user.name = "Pete"; // OK 👍
```

🛑 Ce qui est constant, c’est la référence, pas le contenu de l’objet !

## 📄 5. Copier un objet (clonage superficiel)

🔁 Méthode 1 : Boucle for...in

```js
let clone = {};
for (let key in user) {
  clone[key] = user[key];
}
```

🔁 Méthode 2 : Object.assign()

```js
let clone = Object.assign({}, user);
```

🔁 Méthode 3 : spread syntax ...

```js
let clone = { ...user };
```

🎯 Ces méthodes font une copie superficielle (les sous-objets sont toujours partagés) :

```js
let user = {
  name: "John",
  sizes: { height: 180 }
};

let clone = Object.assign({}, user);
user.sizes.height = 200;

alert(clone.sizes.height); // 200 ❗
```

## 🌊 6. Copier un objet (clonage profond)

🧠 Pour séparer complètement tous les niveaux, on utilise :
✅ structuredClone() (native JS)

```js
let deepClone = structuredClone(user);
```

✅ Gère les objets imbriqués
✅ Gère les références circulaires
❌ Ne clone pas les fonctions

```js
let user = {
  name: "John",
  sizes: { height: 180 }
};

let clone = structuredClone(user);
user.sizes.height = 200;

alert(clone.sizes.height); // 180 ✅
```

## 🛠️ 7. Résumé rapide

|Type de copie| Méthode| Objets imbriqués séparés ?|
---|---|---
|Référence| let b = a| ❌ Non|
|Copie superficielle| Object.assign, ...| ❌ Non|
|Copie profonde| structuredClone()| ✅ Oui|