
# 🧾 Cheat-Sheet – Méthodes de tableau JavaScript

## 🧩 Ajouter / Supprimer des éléments

🔹 **`push(...items)`** : ajoute à la fin  
🔹 **`pop()`** : supprime à la fin  
🔹 **`shift()`** : supprime au début  
🔹 **`unshift(...items)`** : ajoute au début  

```js
let fruits = ["🍎", "🍌"];
fruits.push("🍓"); // ["🍎", "🍌", "🍓"]
fruits.pop();      // ["🍎", "🍌"]
```

---

## ✂️ `splice()` : Ajouter, supprimer ou remplacer

**Syntaxe** : `arr.splice(start, deleteCount, ...items)`

🔸 Supprimer :
```js
let arr = ["I", "study", "JS"];
arr.splice(1, 1); // ["I", "JS"]
```

🔸 Remplacer :
```js
arr.splice(0, 2, "Let's", "dance"); // ["Let's", "dance", "JS"]
```

🔸 Ajouter sans supprimer :
```js
arr.splice(1, 0, "💃"); // ["Let's", "💃", "dance", "JS"]
```

📌 **Index négatifs** autorisés :
```js
arr.splice(-1, 0, "🎉");
```

---

## 🍰 `slice()` : Copier une portion

**Syntaxe** : `arr.slice(start, end)` (end exclu)

```js
let arr = ["🍏", "🍊", "🍒", "🍇"];
arr.slice(1, 3); // ["🍊", "🍒"]
arr.slice(-2);   // ["🍒", "🍇"]
```

📌 `arr.slice()` sans argument = copie complète ✨

---

## ➕ `concat()` : Fusionner des tableaux

```js
let arr = [1, 2];
arr.concat([3, 4], 5); // [1, 2, 3, 4, 5]
```

🧠 Peut fusionner des objets **array-like** si `Symbol.isConcatSpreadable` est défini :

```js
let arrayLike = {
  0: "hello", 1: "world", length: 2,
  [Symbol.isConcatSpreadable]: true
};
arr.concat(arrayLike); // [1, 2, "hello", "world"]
```

---

## 🔁 `forEach()` : Exécuter une fonction pour chaque élément

```js
["Bilbo", "Gandalf", "Nazgul"].forEach((item, i) => {
  console.log(`${item} est à l'index ${i} 📍`);
});
```

📌 Ne retourne rien (undefined)

---

## 🔍 Recherche dans un tableau

### `indexOf()` / `lastIndexOf()` / `includes()`
```js
let arr = [1, 0, false];

arr.indexOf(0);     // 1
arr.includes(false); // true
arr.indexOf(NaN);    // -1 ❌
arr.includes(NaN);   // true ✅
```

### `find()` : Trouver un élément par condition

```js
let users = [
  {id: 1, name: "Alice"}, 
  {id: 2, name: "Bob"}
];

let user = users.find(u => u.id === 1);
console.log(user.name); // Alice
```

### `findIndex()` / `findLastIndex()`
```js
let names = [{name: "John"}, {name: "Pete"}, {name: "John"}];

names.findIndex(u => u.name === "John");     // 0
names.findLastIndex(u => u.name === "John"); // 2
```

---

## 🧹 `filter()` : Obtenir tous les éléments qui passent un test

```js
let users = [
  {id: 1, name: "Alice"}, 
  {id: 2, name: "Bob"},
  {id: 3, name: "Alice"}
];

let alices = users.filter(u => u.name === "Alice");
console.log(alices.length); // 2
```

---

## 🔄 `map()` : Transformer chaque élément

```js
let names = ["Bilbo", "Gandalf", "Nazgul"];
let lengths = names.map(name => name.length); // [5, 7, 6]
```

---

## 🧮 `sort()` : Trier un tableau (par défaut en tant que chaînes)

```js
let nums = [1, 2, 15];
nums.sort();        // [1, 15, 2] ❌
nums.sort((a, b) => a - b); // [1, 2, 15] ✅
```

---
