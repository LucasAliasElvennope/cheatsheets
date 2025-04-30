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

## 🤖 Insertion automatique de point-virgule (ASI)

- JavaScript ajoute parfois un ; automatiquement si tu l’oublies.

- Cela peut marcher... ou provoquer des erreurs étranges.

- ✅ Conseil : mets toujours tes points-virgules.

## 📝 Les commentaires

Sur une ligne :

// Ceci est un commentaire

Sur plusieurs lignes :

```js
/*
  Ceci est un commentaire
  sur plusieurs lignes
*/
```

## 🌐 Découvrir l'écosystème JavaScript

### 🔒 use strict — mode strict

- Active un mode plus sécurisé du langage (ES5+).

- À placer en haut du fichier ou d'une fonction :

```js
"use strict";
```

- Empêche certaines erreurs silencieuses (par exemple, déclarer une variable sans let/const/var).

## 🧑‍🔬 Qu'est-ce que le TC39 ?

- Un groupe de travail chargé de faire évoluer JavaScript.

- Ils proposent, débattent et valident les nouveautés du langage.

## 📘 Qu'est-ce que ECMA-262 ?

- C’est le document officiel qui définit la norme ECMAScript.

- Il décrit tout ce que doit contenir un moteur JavaScript.

### 🧭 Quelle est la version actuelle du standard ECMAScript ?

- Une nouvelle version sort chaque année.

- La version actuelle est généralement notée ES202x (par exemple ES2024).

- 🔎 Consulte régulièrement tc39.es pour suivre les nouveautés.

## 🧮 Les variables en JavaScript

### 📦 Qu'est-ce qu'une variable ?

Une variable est un conteneur dans lequel on peut stocker des données (comme du texte, des nombres, etc.).

### 🏷️ Mots-clés pour déclarer une variable

- let 👉 pour une variable modifiable (à utiliser dans la majorité des cas)

- const 👉 pour une variable qu’on ne veut pas modifier

- var 👉 ancienne façon de déclarer une variable (à éviter aujourd’hui)

#### 🔧 Exemple :

```js
let nom = "Alice";
const age = 30;
```

### 💡 Règles de nommage :

- Les noms doivent commencer par une lettre, $ ou _

- Pas d’espaces ni de caractères spéciaux

- Utilise le camelCase : monNomDeVariable

### 🎯 Utilisation d'une variable avec alert :

```js
let message = "Hello";
alert(message);  // Affiche une boîte avec "Hello"
```

### 🛠️ Modifier une variable :

```js
let score = 0;
score = score + 1; // score devient 1
```

### 🚫 const ne peut pas être modifiée :

```js
const nom = "Alice";
nom = "Bob"; // ❌ Erreur ! nom est une constante
```

### Exemple de message au clic de bouton

Pour afficher un message lorsqu'un utilisateur clique sur un bouton, tu peux utiliser l'exemple suivant :
HTML

```html
<button id="monBouton">Cliquez-moi!</button>
```

JavaScript

```js
document.getElementById("monBouton").addEventListener("click", function() {
  alert("Hello, vous avez cliqué sur le bouton !");
});
```

Explication :

- `getElementById("monBouton")` : Sélectionne le bouton en utilisant son ID.

- `addEventListener("click", function() {...})` : Ajoute un événement click qui exécute une fonction lorsqu'on clique sur le bouton.

- `alert("Hello, vous avez cliqué sur le bouton !")` : Affiche un message à l'utilisateur dans une fenêtre popup.

Une analogie avec la vie réelle

Une variable peut être comparée à une boîte avec un nom dessus, et cette boîte peut contenir des données.

Par exemple, la variable message est comme une boîte étiquetée "message" qui contient "Hello!".

On peut modifier le contenu de cette boîte autant de fois qu'on veut :

```js
let message = 'Hello!';
message = 'World!'; // valeur changée
alert(message); // affiche "World!"
```

### On peut aussi copier la valeur d'une variable dans une autre :

```js
let hello = 'Hello world!';
let message = hello; // copie la valeur de hello
alert(hello);  // Hello world!
alert(message); // Hello world!
```

### Nom de variable

Il existe deux limitations pour un nom de variable en JavaScript :

- Le nom ne doit contenir que des lettres, des chiffres, et les symboles $ et _.

- Le premier caractère ne doit pas être un chiffre.

### Noms valides :

```js
let userName;
let test123;
```

Lorsque le nom contient plusieurs mots, on utilise souvent le camelCase : chaque mot après le premier commence par une majuscule.

Exemple : monTresLongNom

Les symboles $ et _ peuvent également être utilisés dans les noms, sans signification particulière. Exemples valides avec symboles :

```js
let $ = 1;
let _ = 2;
alert($ + _); // 3
```

### Noms invalides :

```js
let 1a; // ne peut pas commencer avec un chiffre
let mon-nom; // un trait d'union '-' n'est pas autorisé
```

🚫 Noms réservés

Certains mots sont réservés par JavaScript et ne peuvent pas être utilisés comme noms de variables. Par exemple, des mots comme let, class, return, function sont déjà utilisés par le langage.

Exemples d'erreurs de syntaxe :

```js
let let = 5; // erreur : "let" est un mot réservé
let return = 5; // erreur : "return" est un mot réservé
```

## Les Constantes

Une constante est une variable dont la valeur ne peut pas être modifiée.
Résumé sur les constantes en JavaScript :

- Déclaration : Pour déclarer une constante, on utilise const au lieu de let. Une constante ne peut pas être réaffectée après sa déclaration.

```js
const myBirthday = '18.04.1982';
myBirthday = '01.01.2001'; // ❌ Erreur : ne peut pas réassigner une constante
```

Utilisation des majuscules : Les constantes sont souvent nommées en majuscules avec des underscores (par exemple, COLOR_RED) pour les valeurs fixes comme des couleurs hexadécimales.

```js
const COLOR_RED = "#F00";
const COLOR_BLUE = "#00F";
let color = COLOR_RED;
alert(color); // Affiche #F00
```

- Constantes dynamiques : Une constante peut aussi être calculée pendant l'exécution, mais sa valeur ne change pas après l'assignation.

```js
const pageLoadTime = 120; // Temps de chargement de la page, mais il reste constant après l'assignation.
```

### Bénéfices :

- Utiliser des constantes avec des majuscules rend le code plus lisible et facilite la maintenance.

- Celles-ci sont plus significatives (par exemple, COLOR_RED est plus compréhensible que #F00).