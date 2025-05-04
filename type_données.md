# 📝 Cheat-Sheet : Types de données en JavaScript

En JavaScript, chaque valeur a un type, comme un texte (chaîne de caractères) ou un nombre. Il y a huit types de données différents, mais on les verra plus en détail plus tard.

Une particularité de JavaScript est qu’on peut changer le type d'une variable à tout moment. Par exemple, une variable peut d'abord être un texte, puis devenir un nombre.

Exemple :

```js
let message = "hello"; // message est un texte
message = 123456; // maintenant, message est un nombre
```

Cela fait de JavaScript un langage typé dynamiquement, ce qui signifie que les variables ne sont pas fixées à un type particulier et peuvent changer selon les besoins.

## Types de données :

- Nombre (number)
- BigInt (bigInt)
- Texte (string)
- Booléen (boolean)
- Null
- Undefined
- Objet et symbol (object and symbol)

---

### Le type Number (nombre)

En JavaScript, on utilise le type number pour tous les nombres :

- les entiers comme 123
- les nombres à virgule comme 12.345

```js
let n = 123;
n = 12.345;
```

Tu peux faire des opérations classiques avec les nombres :

- addition +
- soustraction -
- multiplication *
- division /
etc.

```js
let a = 10;
let b = 5;

let addition = a + b;      // 10 + 5 = 15
let soustraction = a - b;  // 10 - 5 = 5
let multiplication = a * b; // 10 * 5 = 50
let division = a / b;      // 10 / 5 = 2

console.log("Addition :", addition);
console.log("Soustraction :", soustraction);
console.log("Multiplication :", multiplication);
console.log("Division :", division);
```

### Valeurs spéciales du type number

Il y a aussi des cas particuliers dans ce type :

### ✅ Infinity

C’est une valeur spéciale qui représente l’infini.
Par exemple, si tu divises par zéro :

```js
alert(1 / 0); // Affiche Infinity
```

### ❌ NaN (Not a Number)

Cela veut dire "ce n’est pas un nombre".
Tu obtiens NaN si tu fais un calcul impossible, comme :

```js
alert("texte" / 2); // Affiche NaN
```

### Et si tu fais un autre calcul avec NaN, tu obtiens encore NaN :

```js
alert(NaN + 1); // NaN
alert(3 * NaN); // NaN
```

### 🧠 Petit fait curieux : NaN ** 0 (NaN puissance 0) donne 1.

Même si Infinity et NaN ne sont pas des nombres normaux, ils font partie du type number en JavaScript.

---

### Le type `BigInt`

En JavaScript, le type number ne peut pas représenter correctement des très grands nombres entiers. Il y a une limite :
➡️ 9007199254740991 (c’est 2⁵³ - 1).
Au-delà de ça, les résultats peuvent devenir imprécis.

Exemple :

```js
console.log(9007199254740991 + 1); // 9007199254740992
console.log(9007199254740991 + 2); // aussi 9007199254740992 😱
```

### 🔸 Ici, tu vois qu’on ajoute +1 et +2, mais on obtient le même résultat !

Solution : utiliser BigInt

Pour manipuler de très grands nombres entiers, on utilise le type BigInt, ajouté récemment à JavaScript.
Comment créer un BigInt :

### Tu ajoutes simplement un n à la fin du nombre :

```js
const big = 1234567890123456789012345678901234567890n;
```

✅ Grâce à BigInt, tu peux faire des calculs sur des nombres énormes, sans perte de précision.

👉 Ce type est surtout utile pour la cryptographie, les calculs scientifiques ou les horloges très précises.

---

### Le type `String` (texte)

Une chaîne de caractères en JavaScript doit être entre guillemets.

```js
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

En JavaScript, il existe 3 types de guillemets.

- Double quotes: "Hello".
- Single quotes: 'Hello'.
- Backticks: `Hello`.

Les guillemets simples et doubles sont des guillemets “simples”. Il n’y a pratiquement pas de différence entre eux en JavaScript.

Les backticks sont des guillemets “à fonctionnalité étendue”. Ils nous permettent d’intégrer des variables et des expressions dans une chaîne en les encapsulant dans ${…}, par exemple :

```js
let name = "John";

// une variable encapsulée
alert( `Hello, ${name}!` ); // Hello, John!

// une expression encapsulée
alert( `the result is ${1 + 2}` ); // le résultat est 3
```

L’expression à l’intérieur de ${…} est évaluée et le résultat devient une partie de la chaîne. On peut y mettre n’importe quoi : une variable comme name ou une expression arithmétique comme 1 + 2 ou quelque chose de plus complexe.

Veuillez noter que cela ne peut être fait que dans les backticks. Les autres guillemets ne permettent pas une telle intégration !

```js
alert( "the result is ${1 + 2}" ); // le résultat est ${1 + 2} (les doubles quotes ne font rien)
```
---

### Le type `Boolean` (booléen)

Un boolean sert à représenter une réponse oui ou non ✅❌
Il n’a que deux valeurs possibles :

- ✅ true → signifie oui / vrai
- ❌ false → signifie non / faux

Exemple :

```js
let nameFieldChecked = true;  // ✅ le champ "nom" est coché
let ageFieldChecked = false;  // ❌ le champ "âge" n'est pas coché
```

### 🔍 Comparaison logique

Les booléens apparaissent aussi dans les comparaisons :

```js
let isGreater = 4 > 1;
console.log(isGreater); // ✅ true
```

➡️ Ici, 4 > 1 est vrai, donc le résultat est true.

### 🧠 À retenir :

- Les booléens sont très utilisés dans les conditions, les tests, les formulaires, etc.
- Tu verras plus tard comment les combiner avec des opérateurs logiques (&&, ||, !)

---

### 🕳️ La valeur spéciale `null`

- null est une valeur spéciale qui signifie :
👉 "rien", "vide" ou "valeur inconnue"

- Ce n’est pas un objet ou un pointeur comme dans d’autres langages.

### 🧪 Exemple :

```js
let age = null;
```

➡️ Ici, ça veut dire :

🧍 "Je connais la variable age, mais je ne connais pas encore sa valeur."

### ✅ À retenir :

- null est un type à part entière, différent des autres types (number, string, etc.).
- Tu l’utilises quand tu veux dire : "il n’y a rien pour l’instant".

---

### ❓ La valeur spéciale `undefined`

- undefined signifie :
👉 "aucune valeur n’a été attribuée"

- C’est un type à part entière, tout comme null.

### 🧪 Exemple :

```js
let age;
console.log(age); // ❓ undefined
```

➡️ Ici, on a déclaré la variable age,
mais on n’a rien mis dedans → donc sa valeur est undefined.
⚠️ Peut-on écrire undefined soi-même ?

Oui, mais ce n’est pas recommandé :

```js
let age = 100;
age = undefined; // possible, mais déconseillé
```

### 🧠 Mieux vaut utiliser null pour dire que la variable est vide volontairement.

### 🔍 Résumé null vs undefined

| Valeur	| ✨ Signifie	| 🛠️ Quand l’utiliser ? |
|---|---|---|
| undefined	| La variable n’a pas encore de valeur	| Par défaut, quand on déclare une variable sans l'initialiser |
| null	| La variable est vide volontairement	| Quand on veut dire : “il n’y a rien” ou “valeur inconnue” |

---

### 🏷️ Le type `Object` (objet)

Les objets sont différents des types primitifs (comme les nombres, chaînes de caractères, etc.).

- Les types primitifs ne peuvent contenir qu'une seule valeur (par exemple, un nombre ou une chaîne de caractères).

- Les objets permettent de stocker des collections de données ou des entités plus complexes.

💼 Exemple d'objet :

```js
let user = {
  name: "Alice",
  age: 30,
  isAdmin: true
};
```

🔸 Ici, user est un objet qui contient plusieurs données :

- Le nom de l'utilisateur : "Alice"
- Son âge : 30
- Et s’il est administrateur : true

---

### 🔑 Le type `Symbol` (symbole)

Le type Symbol est utilisé pour créer des identificateurs uniques pour les objets.

- Un symbol est comme une étiquette unique qu’on peut utiliser pour nommer des propriétés d’objets.

- Il garantit que deux symboles ne seront jamais égaux, même si leurs noms sont identiques.

🔨 Exemple de symbole :

```js
const sym = Symbol("description");
let obj = {
  [sym]: "value"
};

console.log(obj[sym]); // "value"
```

🔸 Ici, sym est un identifiant unique utilisé comme clé pour l’objet obj.

### 🚀 Résumé

- Objects servent à stocker des collections de données ou des entités complexes.
- Symbols servent à créer des identificateurs uniques pour des propriétés d'objets.

---

## L'opérateur typeof

### 🔎 typeof — Connaître le type d'une valeur

L'opérateur typeof sert à connaître le type d'une variable ou d'une valeur 📦.
Il renvoie une chaîne de caractères 🎯 qui décrit le type.
💡 Syntaxe :

```js
typeof valeur;
```

🧪 Exemples utiles :

| Exemple	| Résultat	| Explication |
|---|---|---|
| typeof 42	| "number" | C’est un nombre |
| typeof "hello"	| "string" | C’est une chaîne de texte |
| typeof true	| "boolean" | C’est vrai ou faux |
| typeof undefined	| "undefined" | Non défini, pas de valeur |
| typeof 10n	| "bigint" | Très grand nombre entier |
| typeof Symbol("id")	| "symbol" | Identifiant unique |
| typeof Math	| "object" | Objet spécial pour les maths |
| typeof null	| "object" | (Erreur historique) |
| typeof alert	| "function" | C’est une fonction |


⚠️ À retenir !

- 🧊 null retourne "object" ❌ → c’est une vieille erreur de JavaScript.
- 🧮 Math est un objet spécial avec des fonctions mathématiques.
- 📢 alert est une fonction, donc typeof retourne "function" (même si en réalité, les fonctions sont aussi des objets).

### ✅ Exemple d’utilisation :

```js
let age = 25;

if (typeof age === "number") {
  console.log("🎉 C’est un nombre !");
}
```
