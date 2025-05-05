# 🌿 Les branches conditionnelles : if, ?

En JavaScript, il arrive souvent qu’on doive exécuter du code seulement si une condition est remplie (par exemple : si un utilisateur est majeur ou non).
Pour cela, on utilise deux grands outils :

- `if` ➡️ exécuter un bloc de code si une condition est vraie

- `?` (opérateur ternaire) ➡️ choisir rapidement entre deux valeurs selon une condition

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

Si elle est fausse (false), le bloc est ignoré.


## 🧱 Plusieurs instructions ? Toujours des {} !

Si tu veux exécuter plusieurs lignes à l’intérieur du if, utilise toujours des accolades `{}` :

```js
if (year == 2015) {
  alert("C'est exact ✅");
  alert("Tu es trop fort ! 💪");
}
```

👀 Même s’il n’y a qu’une seule ligne, il est recommandé de toujours utiliser les {} pour éviter les bugs et améliorer la lisibilité.

---

## 🧮 Conversion booléenne automatique

JavaScript évalue la condition à l’intérieur du if (...) et la convertit en true ou false.

**💡 Rappel** : certaines valeurs sont automatiquement considérées comme "fausses" (falsy) et d’autres comme "vraies" (truthy).

| ❌ Falsy	| ✅ Truthy	|
| --- | --- |
| 0	| tout nombre ≠ 0 |
| "" (chaîne vide)	| chaîne non vide |
| null	| undefined	|
| NaN	|

### 🧪 Exemple :

```js
if (0) {
  // ❌ ne sera jamais exécuté
}

if (1) {
  // ✅ sera exécuté
}
```

### Ou encore :

```js
let cond = (year == 2015); // renvoie true ou false

if (cond) {
  alert("Bonne réponse !");
}
```

## 🔀 else : si la condition est fausse

Tu peux ajouter un bloc else pour exécuter du code quand la condition est fausse :

### 🧠 Exemple :

```js
if (year == 2015) {
  alert("Bonne réponse ✅");
} else {
  alert("Dommage ❌");
}
```

## 🔀 else if : plusieurs conditions

Tu veux tester plusieurs cas différents ? Utilise else if :

```js
let year = prompt("En quelle année ECMAScript-2015 est sorti ?");

if (year < 2015) {
  alert("Trop tôt ⏰");
} else if (year > 2015) {
  alert("Trop tard 🕰️");
} else {
  alert("Exactement 🎯");
}
```

**👉 JavaScript vérifie les conditions dans l’ordre. Il s’arrête dès qu’une est vraie.**

Tu peux enchaîner autant de else if que tu veux. Le else final est optionnel, mais souvent utile.