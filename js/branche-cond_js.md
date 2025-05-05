# 🌿 Les branches conditionnelles : if, ?

En JavaScript, il arrive souvent qu’on doive exécuter du code seulement si une condition est remplie (par exemple : si un utilisateur est majeur ou non).
Pour cela, on utilise deux grands outils :

- if ➡️ exécuter un bloc de code si une condition est vraie

- ? (opérateur ternaire) ➡️ choisir rapidement entre deux valeurs selon une condition

## 🔍 if (...) : tester une condition

```js
if (condition) {
  // code à exécuter si la condition est vraie ✅
}
```

### 🧠 Exemple simple :

```js
let year = prompt("En quelle année ECMAScript 2015 est sorti ?");

if (year == 2015) {
  alert("Tu as raison ! 🎉");
}
```

📌 Ici, year == 2015 est la condition.

Si elle est vraie (true), alors le bloc à l’intérieur de { ... } est exécuté.