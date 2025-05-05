
# 🧠 Cheat-Sheet : Les Variables en JavaScript

## 🗃️ Qu’est-ce qu’une variable ?

Une variable est comme une boîte nommée 📦 qui sert à stocker des données dans un programme.

`📌 Exemple` :

```js
let message = 'Hello';
alert(message); // Affiche "Hello"
```

## 🔧 Déclaration d’une variable

👉 On déclare une variable avec let, comme ceci :

```js
let message;
message = 'Hello!';
```

Ou tout en une ligne :

```js
let message = 'Hello!';
```

## 🏳️ Plusieurs variables

On peut déclarer plusieurs variables :

```js
let user = 'John';
let age = 25;
let message = 'Hello';
```

## 🔍 Éviter :

```js
let user = 'John', age = 25, message = 'Hello'; // Moins lisible
```

## 📦 Analogie réelle

Imagine une boîte avec une étiquette "message" sur laquelle tu colles un mot.
Tu peux changer ce mot quand tu veux :

```js
let message = 'Hello!';
message = 'World!';
```

## 📢 Résultat : alert(message); affiche "World!"

## 🔄 Copier une valeur

```js
let hello = 'Hello world!';
let message;

message = hello; // Copie la valeur
```

Les deux contiennent "Hello world!"

## 🚨 Attention : redéclaration interdite

```js
let message = "Hi";
// let message = "Hello"; ❌ Erreur ! Déjà déclaré
```

## 🧓 var : l’ancienne façon

```js
var message = "Hello";
```

### ⚠️ À éviter aujourd’hui. Utilise let ou const à la place.

### ❗ Affectation sans déclaration

Sans "use strict" :

```js
num = 5; // Fonctionne mais dangereux ❌
```

Avec "use strict" :

```js
"use strict";
num = 5; // ❌ Erreur : num non défini
```

## 🧊 Constantes (const)

```js
const myBirthday = '18.04.1982';
```
    
## 🛑 Ne peut pas être modifiée :

```js
myBirthday = '01.01.2001'; // ❌ Erreur
```

## 🔠 Constantes en MAJUSCULES

```js
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";

let color = COLOR_RED;
```

### ✅ Avantages :

- Plus clair à lire

- Moins de risque d’erreur

- Donne un sens à la valeur

### ⚠️ MAJUSCULES ou non ?

- const PI = 3.14; ✅ → connu à l’avance

- const pageLoadTime = ...; ✅ → connu pendant l'exécution, donc pas en majuscules

## 🧼 Nommage des variables

### 🎯 Règles de base :

- Lettres, chiffres, $, _

- Ne pas commencer par un chiffre

- Pas d’espaces, pas de tiret -

### ✔️ Valide :

```js
let userName;
let $ = 1;
let _ = 2;
```

### ❌ Invalide :

```js
let 1a;
let mon-nom;
```

## 🧠 Bonnes pratiques de nommage

- 🔤 Utiliser le camelCase : userName, shoppingCart

- ❌ Éviter a, b, data, value → trop vagues

- ✅ Utiliser des noms descriptifs et précis

- 👥 Se mettre d’accord avec son équipe sur les noms

## 🈲 Mots réservés

Ne pas utiliser les mots-clés du langage comme noms de variable :

```js
let let = 5;     // ❌ Erreur
let return = 42; // ❌ Erreur
```

## 🌍 Caractères non latins

Possible mais déconseillé :

```js
let имя = 'Alex';
let 我 = 'Ni hao';
```

## 📌 Préfère l’anglais pour des raisons de lisibilité universelle 🌐

## 🔁 Réutiliser ou créer ?

## 🙅 Mauvaise pratique :

```js
let data = 5;
data = "Bonjour"; // Changement de type
```

## 👍 Meilleure approche :
Crée une nouvelle variable si c’est une nouvelle idée. Plus clair, plus sûr, plus maintenable.

## 🧾 Résumé

| Mot-clé	| Peut changer ?	| Recommandé ?	| Utilisation |
| ---	| ---	| ---	| --- |
| let	| ✅ Oui	| ✅ Oui	| Valeur qui peut changer |
| const	| ❌ Non	| ✅ Oui	| Valeur fixe (ex : couleur) |
| var	| ✅ Oui	| ❌ Non	| Ancien code (à éviter) |

## 🧠 Astuce finale :

    ✨ Bien nommer une variable, c’est déjà à moitié coder.