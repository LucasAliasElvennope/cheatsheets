# 🟨 Première introduction au langage JavaScript

## 📌 Comprendre la structure du code et la syntaxe

### 🔄 EcmaScript vs JavaScript
- **JavaScript** est le langage utilisé dans les navigateurs.
- **EcmaScript (ES)** est la **norme** (standard) qui définit les règles de JavaScript.
- JavaScript suit donc les versions du standard ECMAScript (ES5, ES6/ES2015, etc.).

### ✒️ L'importance de la ponctuation
- Le **point-virgule (`;`)** termine généralement une **instruction**.
- Même si JavaScript peut l’ajouter automatiquement (voir plus bas), **mieux vaut l’écrire** pour éviter les bugs.

### ⚙️ Standard & Environnement d'exécution
- ECMAScript définit **le langage**.
- L’environnement d’exécution (navigateur, Node.js, etc.) fournit **les outils autour**, comme les API DOM, `fetch`, etc.

### 🧱 Qu'est-ce qu'une instruction ?
> Une **instruction** est une action que le navigateur exécute, comme stocker une valeur ou afficher un message.

Exemples :
```js
let x = 10;
console.log(x);
```

### 🤖 Insertion automatique de point-virgule (ASI)

- JavaScript ajoute parfois un `;` automatiquement si tu l’oublies.

- Cela peut marcher... ou provoquer des erreurs étranges.

- ✅ Conseil : mets toujours tes points-virgules.

### 📝 Les commentaires

Sur une ligne :

```js
// Ceci est un commentaire
```

Sur plusieurs lignes :

```js
/*
  Ceci est un commentaire
  sur plusieurs lignes
*/
```

### 🌐 Découvrir l'écosystème JavaScript

### 🔒 use strict — mode strict

- Active un mode plus sécurisé du langage (ES5+).

- À placer en haut du fichier ou d'une fonction :

```js
"use strict";
```

- Empêche certaines erreurs silencieuses (par exemple, déclarer une variable sans `let/const/var`).

### 🧑‍🔬 Qu'est-ce que le TC39 ?

- Un groupe de travail chargé de faire évoluer JavaScript.

- Ils proposent, débattent et valident les nouveautés du langage.

### 📘 Qu'est-ce que ECMA-262 ?

- C’est le document officiel qui définit la norme ECMAScript.

- Il décrit tout ce que doit contenir un moteur JavaScript.

### 🧭 Quelle est la version actuelle du standard ECMAScript ?

- Une nouvelle version sort chaque année.

- La version actuelle est généralement notée ES202x (par exemple ES2024).

- 🔎 Consulte régulièrement tc39.es pour suivre les nouveautés.
