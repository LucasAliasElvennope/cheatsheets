# 🧠 Les types de données en JavaScript

Chaque valeur en JavaScript a un type 📦

`Exemples` : un nombre 🧮, une chaîne de caractères ✉️, un booléen 🔘, etc.

📊 Typage dynamique

JavaScript est un langage à typage dynamique :
➡️ Une variable peut changer de type à tout moment.

```js
let message = "hello"; // 📩 chaîne de caractères
message = 123456;      // 🔢 nombre
```

## 🔢 1. Number

Utilisé pour nombres entiers ou décimaux.

```js
let n = 123;       // entier
n = 12.345;        // décimal
```

Opérations possibles : +, -, *, /, %, etc.

Valeurs spéciales :

| Valeur	| Signification |
| --- | --- |
| Infinity	|♾️ Résultat d’une division par 0 |
| -Infinity	|♾️ Négatif infini |
| NaN	|❌ Erreur de calcul (Not a Number) |

```js
alert(1 / 0);              // Infinity
alert("hello" / 2);        // NaN
alert(NaN + 1);            // NaN
```

### 🧠 Astuce : les opérations sur NaN produisent toujours... NaN !

## 🧮 2. BigInt

Pour des entiers très grands (au-delà de ±(2⁵³-1))
➡️ Utile en cryptographie, horodatage, etc.

```js
const big = 123456789012345678901234567890n;
```

### ⚠️ Pas supporté par Internet Explorer ❌

## 📝 3. String

Chaîne de caractères entre '', "" ou ` (backticks).

```js
let str1 = "Hello";
let str2 = 'Bonjour';
let phrase = `Salut ${str1}!`; // 🔁 interpolation
```

💡 Seuls les backticks permettent d’intégrer du JavaScript :

```js
let name = "Lucas";
alert(`Salut ${name}!`); // 👋
```

## ✅ 4. Boolean

Type logique : true ✅ ou false ❌

Utilisé pour les conditions :

```js
let isAdult = true;
let isMinor = false;

let result = 5 > 3; // true
```

## 🕳️ 5. null

Représente une valeur vide ou inconnue.

```js
let age = null; // 🤷‍♂️ âge inconnu
```

### 🚫 Ce n’est PAS un objet !

## 🚫 6. undefined

Valeur d’une variable non définie.

```js
let name;
alert(name); // undefined
```

🛑 Ne pas l’assigner volontairement → préférer null.

## 🆔 7. Symbol

Permet de créer des identifiants uniques 🔑
(Utile pour les objets, vu plus tard)

```js
let id = Symbol("id");
```

## 🧱 8. Object (non primitif)

Permet de stocker des données complexes : tableaux, fonctions, etc.
➡️ On le verra plus tard en détail !

## 🔎 L'opérateur typeof

Renvoie le type d’une valeur ➡️ sous forme de string :

```js
typeof "hello"    // "string"
typeof 42         // "number"
typeof true       // "boolean"
typeof undefined  // "undefined"
typeof null       // "object" ❗ (erreur historique)
typeof Symbol()   // "symbol"
typeof alert      // "function"
```

💡 typeof x === typeof(x) ✅

## 🧾 Résumé

| Type	| Description |
| --- | --- |
| number	| Nombres entiers/décimaux |
| bigint	| Très grands entiers |
| string	| Chaînes de caractères |
| boolean	| Vrai / Faux |
| null	| Valeur vide / inconnue |
| undefined	| Pas encore défini |
| symbol	| Identifiant unique |
| object	| Données complexes (objets, arrays…) |