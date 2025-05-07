# 🧱 Les Objets en JavaScript

## 📌 C’est quoi un objet ?

Un objet est une structure spéciale qui permet de stocker plusieurs valeurs ensemble, qui fonctionne sous forme de paires clé/valeur.

***🧊 Contrairement aux types primitifs (comme les nombres, les chaînes…), les objets peuvent contenir plusieurs données variées — comme une boîte de rangement avec des étiquettes ! 📦🏷️***


**🗃️ Métaphore :**

Pense à un objet comme une armoire de bureau :

- Chaque tiroir (= clé 🔑) a une étiquette (le nom).

- À l’intérieur, il y a un fichier (= valeur 📄).

- Tu peux ajouter, modifier, ou supprimer ces fichiers facilement !

## ✍️ Créer un objet

Il existe deux façons de créer un objet vide :

```js
let monObjet = {};         // ✅ façon courte
let monObjet = new Object(); // ✅ façon plus "classique"
```

## 📚 En résumé :

- ✅ Clé = nom de la propriété (toujours une chaîne 🧾)

- ✅ Valeur = n’importe quel type de donnée : nombre, chaîne, booléen, fonction, tableau, objet…

---

## 🧾 Objets : littéraux et propriétés

### 🧱 Créer un objet avec des propriétés

Tu peux définir directement des propriétés dans un objet avec des accolades {} :

```js
let user = {
  name: "John",  // clé : "name", valeur : "John"
  age: 30        // clé : "age", valeur : 30
};
```

***👆 C’est ce qu’on appelle un littéral d’objet !***

#### 🔑 Propriétés = paires clé/valeur

Chaque propriété dans un objet est une paire :

- 🔑 Clé (ou nom / identifiant) ➜ avant les deux-points :

- 📦 Valeur ➜ après les deux-points :

#### 🗃️ Exemple d’armoire :

- "name" = tiroir avec étiquette "name" et contenu "John"

- "age" = tiroir avec étiquette "age" et contenu 30

### 📤 Accéder aux valeurs

Tu peux lire les propriétés avec la notation par point (.) :
```js
alert(user.name); // ➜ "John"
alert(user.age);  // ➜ 30
```

### ➕ Ajouter une propriété

Tu peux aussi ajouter des propriétés après coup :

```js
user.isAdmin = true;
```

### ❌ Supprimer une propriété

Utilise l’opérateur delete :

```js
delete user.age;
```

### 📝 Propriétés à plusieurs mots

Si ta clé contient des espaces ou des caractères spéciaux, utilise des guillemets "..." :

```js
let user = {
  name: "John",
  "likes birds": true
};
```

***La dernière propriété de la liste peut se terminer par une virgule :***

```js
let user = {
  name: "John",
  age: 30,
}
```

#### **Cela s’appelle une virgule “trailing” ou “hanging”. Elle facilite l’ajout/suppression/déplacement des propriétés, car toutes les lignes se ressemblent.**

---

## 🧩 Crochets [] : Accès aux propriétés avancé

### 🛑 Pourquoi les crochets sont utiles ?

Certaines clés dans un objet ne fonctionnent pas avec la notation par point ., par exemple :

```js
user.likes birds = true; // ❌ ERREUR de syntaxe !
```

➡️ JavaScript croit que tu veux accéder à user.likes et il ne comprend pas le mot birds.

### ✅ Solution : la notation entre crochets []

Tu peux utiliser des chaînes de caractères comme clés, même avec :

- des espaces

- des caractères spéciaux

- ou même des valeurs dynamiques (ex. variables)

```js
let user = {};

// Ajouter une propriété
user["likes birds"] = true;

// Lire la propriété
alert(user["likes birds"]); // ✅ true

// Supprimer la propriété
delete user["likes birds"];
```

### 📝 Important :

Les chaînes doivent être entre guillemets '...', "..." ou `...`.

### 🧠 Accès dynamique (variable comme clé)

Tu peux utiliser une variable comme nom de propriété :

```js
let key = "likes birds";
user[key] = true;
```

➡️ C’est comme si tu faisais : user["likes birds"] = true

### 🎯 Exemple plus poussé avec prompt

```js
let user = {
  name: "John",
  age: 30
};

let key = prompt("Que veux-tu savoir sur l'utilisateur ?", "name");

alert(user[key]); // Affiche "John" si l'utilisateur entre "name"
```

✅ Ici, la propriété est choisie dynamiquement selon ce que l'utilisateur écrit !

### ***⚠️ Ne pas confondre avec la notation par point***

```js
let key = "name";
alert(user.key); // ❌ undefined (cherche une propriété appelée "key")
alert(user[key]); // ✅ "John" (utilise la valeur de la variable)
```

### 📌 Résumé rapide

| Situation	| .dot ❌	| ["brackets"] ✅
| ---	| ---	| --- |
| Clé avec espaces	| ❌	| ✅
| Clé avec caractères spéciaux	| ❌	| ✅
| Clé stockée dans une variable	| ❌	| ✅
| Clé définie en dur, simple mot	| ✅	| ✅

---

## 🧮 Propriétés calculées (computed properties)

### 🎯 Qu'est-ce que c'est ?

Quand tu crées un objet, tu peux calculer le nom d'une propriété à l’aide des crochets [] directement dans l’objet !

👉 On appelle ça une propriété calculée.

### 🍏 Exemple simple :

```js
let fruit = prompt("Quel fruit acheter ?", "apple");

let bag = {
  [fruit]: 5
};

alert(bag.apple); // Affiche 5 si l'utilisateur a écrit "apple"
```

### **🔍 Ce que ça fait :**

```js
    Si fruit = "apple" 👉 l'objet devient :

    bag = { apple: 5 }
```

### 🔁 Même chose, version classique :

```js
let fruit = prompt("Quel fruit acheter ?", "apple");
let bag = {};

bag[fruit] = 5;
```

✅ Même résultat, mais la syntaxe avec crochets dans l'objet est plus compacte.

### 💡 Astuce : tu peux calculer des noms plus complexes

```js
let fruit = "apple";

let bag = {
  [fruit + "Computers"]: 5
};

console.log(bag.appleComputers); // 5
```

➡️ Ici, la clé devient "appleComputers" grâce à l'expression.

### ⚠️ À retenir

- ✔️ Les crochets permettent des noms dynamiques 🌀

- ❌ La notation par point . ne permet pas ça

- ✅ Utilise . si la clé est simple et connue d'avance

- ✅ Utilise [] si :

    tu utilises une variable 📦

    tu veux construire dynamiquement une clé 🧠

    tu as des espaces ou caractères spéciaux ❗

---

## 🔡 Valeur de propriété abrégée (Property Value Shorthand)

### 🎯 Quand une propriété d’un objet a le même nom qu’une variable existante…
➡️ Tu peux écrire plus court !

### 🧪 Exemple :

```js
function makeUser(name, age) {
  return {
    name, // au lieu de name: name
    age   // au lieu de age: age
  };
}
```

🎉 C’est identique à :

```js
return {
  name: name,
  age: age
};
```

### 💡 Tu peux mélanger :

```js
let user = {
  name,      // raccourci
  age: 30    // propriété normale
};
```
--- 

## 🚫 Limitations des noms de propriété ?

### 👉 Aucune !

Tu peux utiliser des mots réservés comme :

```js
let obj = {
  for: 1,
  let: 2,
  return: 3
};

alert(obj.for + obj.let + obj.return); // 6
```

✅ Les clés peuvent être n’importe quelle chaîne ou même un symbole (expliqué plus tard).

---

## ❓ Test de propriété avec in

Tu peux tester si une propriété existe dans un objet avec :

"clé" in objet

### Exemple :

```js
let user = { name: "John", age: 30 };

alert("age" in user);      // ✅ true
alert("blabla" in user);   // ❌ false
```

🧠 Tu peux aussi utiliser une variable comme clé :

```js
let key = "age";
alert(key in user); // true
```

---

## 🔁 Boucle for..in (pour les objets)

La boucle for..in permet de **parcourir toutes les clés (propriétés) d’un objet 🧰.

### 📌 Syntaxe :

```js
for (let clé in objet) {
  // Code à exécuter pour chaque propriété
}
```

### 👀 Exemple :

```js
let user = {
  name: "John",
  age: 30,
  isAdmin: true
};

for (let key in user) {
  alert(key);         // 🔑 Affiche la clé : name, age, isAdmin
  alert(user[key]);   // 📦 Affiche la valeur : John, 30, true
}
```

### ✅ Tu peux changer le nom de la variable key :

```js
for (let prop in user) {
  alert(prop); // fonctionne pareil ✅
}
```

### 🧠 À retenir

-    for..in 🔍 parcourt uniquement les clés de l'objet (et pas les valeurs directement).

-    Tu peux accéder à chaque valeur avec objet[clé].

-    Différent de la boucle classique for(;;) ⏳ (utilisée pour les tableaux souvent).

-    Utile pour lire ou manipuler les données d’un objet ℹ️.




