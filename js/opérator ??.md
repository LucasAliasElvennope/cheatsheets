# 🔍 Qu'est-ce que ?? ?

L'opérateur ?? est appelé "opérateur de coalescence des nuls" (nullish coalescing operator).

Il permet de donner une valeur par défaut uniquement si la variable vaut null ou undefined.

## 🧠 Comment ça marche ?

```js
a ?? b
```

**👉 Cela signifie :**

- ✅ Si a n'est pas null/undefined ➡️ retourne a

- ❌ Si a est null ou undefined ➡️ retourne b

## 🔧 Définition de "défini"

Dans ce contexte, une valeur est considérée comme "définie" si elle n'est ni null ni undefined.

**Donc :**

- "Bonjour" ✅ défini

- 0 ✅ défini

- false ✅ défini

- "" (chaîne vide) ✅ défini

- null ❌ pas défini

- undefined ❌ pas défini

## 🧪 Exemples simples

```js
let user;
alert(user ?? "Anonyme"); // 👉 "Anonyme" car user est undefined

user = "Lucas";
alert(user ?? "Anonyme"); // 👉 "Lucas"
```

## 📚 Exemple avec plusieurs variables

```js
let firstName = null;
let lastName = null;
let nickName = "Superdev";

alert(firstName ?? lastName ?? nickName ?? "Anonyme"); // 👉 "Superdev"
```

## 💡 Cela retourne la première valeur définie.

## ❓ Différence avec || (OR logique)

### 🧪 Exemple :

```js
let height = 0;

alert(height || 100); // 👉 100 ❌
alert(height ?? 100); // 👉 0 ✅
```

### Explication :

    || retourne la première valeur "vraie"

        Il considère false, 0, "", null, undefined comme "fausses"

    ?? retourne la première valeur définie (≠ null/undefined)

## 🎯 Donc, ?? est plus précis quand tu veux vérifier si une valeur est vraiment manquante (null ou undefined) et non juste fausse.

## 🏗️ Priorité de ??

Sa priorité est faible (comme ||), donc il faut souvent utiliser des parenthèses :

```js
let height = null;
let width = null;

let area = (height ?? 100) * (width ?? 50); // ✅ 5000
```
### ⚠️ Sans parenthèses, tu peux avoir un résultat incorrect :

```js
let area = height ?? 100 * width ?? 50; // ❌ Mauvais résultat
```

### ⚠️ Interdiction avec || ou && sans parenthèses

JavaScript interdit d’écrire ça :

```js
let x = 1 && 2 ?? 3; // ❌ Erreur de syntaxe
```

Mais tu peux corriger avec des parenthèses :

```js
let x = (1 && 2) ?? 3; // ✅ Résultat : 2
```

## 🧾 Résumé complet

## ✅ L’opérateur ?? :

- Retourne la première valeur définie (≠ null / undefined)

- Très utile pour fournir une valeur par défaut

- ✅ Différent de || qui teste si la valeur est "vraie"

- 📉 Priorité faible → utilise des parenthèses !

- 🚫 Ne pas mélanger directement avec || ou && sans parenthèses

## 🛠️ Exemple final utile

```js
let configHeight = userHeight ?? 100;
```

➡️ Si userHeight est null ou undefined, alors on prendra 100.