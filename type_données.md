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
- Booléen (boolean)
- Texte (string)

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