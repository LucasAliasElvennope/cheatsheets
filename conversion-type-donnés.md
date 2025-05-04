# 🔁 Les conversions de types en JavaScript

En JavaScript, il arrive souvent que des valeurs soient automatiquement converties d’un type à un autre selon le contexte. C’est ce qu’on appelle la conversion de type (ou coercition).

**➡️ Par exemple :**

```js
alert("Le résultat est : " + 2); // "Le résultat est : 2"
```

**👉 Ici, le nombre 2 est converti automatiquement en chaîne de caractères pour être affiché.**

Mais il est aussi possible (et parfois nécessaire) de convertir manuellement les valeurs avec des fonctions comme `String()`, `Number()` ou `Boolean()`. 

## 1. Conversion en chaîne de caractères (type string)

**🔸 Se produit quand :**

- On affiche une valeur (ex: alert, console.log)
- On utilise + avec une chaîne

**🔹 Conversion manuelle :**
```js
let valeur = true;
valeur = String(valeur); // "true"
```

**📝 Résultats typiques :**

- String(null) → "null"
- String(undefined) → "undefined"
- String(123) → "123"

## 2. Conversion en nombre (type number)

**🔸 Se produit dans :**

- Les opérations mathématiques (+, -, /, etc.)
- Des comparaisons numériques

**🔹 Conversion manuelle :**

```js
let str = "42";
let num = Number(str); // 42
```

**📝 Résultats typiques :**

- Valeur d'origine	Résultat de Number(valeur)
- "123"	123
- "123abc"	NaN (pas un nombre)
- true	1
- false	0
- null	0
- undefined	NaN
- " 5 "	5 (espaces ignorés)

## 3. Conversion en booléen (type boolean)

**🔸 Se produit dans :**

- Les conditions (if, while, etc.)
- Les opérations logiques (!, ||, &&)

**🔹 Conversion manuelle :**

```js
Boolean(0);        // false
Boolean("salut");  // true
```

**📝 ⚠️ Résumé des cas :**

- Valeur	Résultat de Boolean(valeur)
- 0, NaN, null, undefined, ""	false ❌
- Toute autre valeur	true ✅

**⚠️ Attention :**

- "0" (une chaîne non vide) donne true
- " " (espace seul) donne aussi true

**🧠 Récapitulatif des règles**

| Type original	| Vers string	| Vers number	| Vers boolean |
| true	| "true"	| 1	| ✅ true |
| false	| "false"	| 0	| ❌ false |
| 0	| "0"	| 0	| ❌ false |
| "123"	| "123"	| 123	| ✅ true |
| null	| "null"	| 0	| ❌ false |
| undefined	| "undefined"	| NaN	| ❌ false |
| "abc"	| "abc"	| NaN	| ✅ true |

## 🧪 Exemples pratiques

```js
alert("5" + 1);        // "51" (concaténation)
alert("5" - 1);        // 4 (soustraction → conversion en number)
alert(Boolean("0"));   // true (chaine non vide)
alert(Number("abc"));  // NaN
```
