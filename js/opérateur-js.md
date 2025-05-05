# 🔧 Qu’est-ce qu’un opérateur ?

Un opérateur est un symbole ou un mot-clé utilisé pour effectuer une opération sur une valeur ou plusieurs valeurs (appelées opérandes) 🔢.

👉 Il sert à manipuler, comparer ou transformer les données (nombres, chaînes, booléens, etc.) dans ton programme.

### 🧠 Exemples simples :

- + additionne deux nombres ➕
    2 + 3 donne 5

- * multiplie deux nombres ✖️
    4 * 5 donne 20

- == compare deux valeurs pour voir si elles sont égales 🤝
    "3" == 3 renvoie true (car conversion automatique)

Voici une version simplifiée, ultra claire et enrichie d’émojis 🧠✨ du chapitre « Opérateurs de base & mathématiques » en JavaScript, parfaite pour ta cheat-sheet !

## 🧮 Opérateurs de base & mathématiques en JS

### 🧱 Termes à connaître

- Opérande : ce à quoi un opérateur est appliqué.
    → Ex: 5 * 2 👉 5 et 2 sont les opérandes.

- Opérateur unaire : agit sur 1 seul opérande.
    → Ex: -x change le signe de x.

- Opérateur binaire : agit sur 2 opérandes.
    → Ex: y - x soustrait x de y.

### ➕➖✖️➗ Opérations mathématiques

Opérateur	| Action	| Exemple	| Résultat
---	| ---	| ---	| ---
+	| Addition	| 3 + 2	| 5 |
-	| Soustraction	| 5 - 1	| 4 |
*	| Multiplication	| 4 * 2	| 8 |
/	| Division	| 10 / 2	| 5 |
%	| Reste (modulo) 🧩	| 5 % 2	| 1 (reste) |
**	| Exponentiation 🔥	| 2 ** 3	| 8 (2³) |

### 🧪 Exemples spéciaux

```js
alert( 4 ** (1/2) ); // √4 = 2
alert( 8 % 3 );      // 2 (reste)
```

### 🔗 Concaténation (chaînes avec +)

Si l’un des deux est une chaîne, ➕ devient concaténation :

```js
'Hello' + 'World'     // "HelloWorld"
'1' + 2               // "12"
2 + 2 + '1'           // "41"
'1' + 2 + 2           // "122"
```

Les autres opérateurs (-, /, *, etc.) forcent les chaînes en nombres :

```js
'6' / '2'             // 3
'6' - 2               // 4
```

### 🔢 Conversion avec le + unaire

Il convertit en nombre :

```js
+true     // 1
+""       // 0
+"2" + +"3"  // 5
```

### 📊 Précédence des opérateurs

Priorité	| Opérateur	| Exemple|
---	| ---	| ---
14	| + unaire, - unaire	| +x, -x|
13	| **	| 2 ** 3|
12	| *, /, %	a * b|
11	| +, - (binaires)	a + b|
2	| = (assignation)	x = 5|


### 🧠 Parenthèses () peuvent changer l’ordre.

### 📝 Affectation (=)

```js
let x = 2 * 3 + 1;  // x = 7
```

= retourne une valeur :

```js
let a = 1, b = 2;
let c = 3 - (a = b + 1); // a=3, c=0
```

### ⛓️ Affectations chaînées

```js
let a, b, c;
a = b = c = 2 + 2;  // tous = 4
```

### ♻️ Modification sur place

```js
let n = 2;
n += 5;   // n = 7
n *= 2;   // n = 14
```

### Autres : -=, /=, %=, **=, etc.

```js
let n = 2;
n += 5;   // n = 7
n *= 2;   // n = 14
```

### ⬆️⬇️ Incrémentation / Décrémentation

```js
let x = 1;
x++;  // x = 2 (postfixe)
++x;  // x = 3 (préfixe)
```

### Forme	Retourne

++x	valeur après
x++	valeur avant

### 🧠 Résumé rapide

| Expression	| Résultat |
| --- | --- |
+"5" | 5 |
'1' + 2 + 2 | "122" |
2 + 2 + '1' | "41" |
6 - '2' | 4 |
let x = 0; ++x | 1 |
let x = 0; x++ | 0 (mais x=1) |

## 🔗 Concaténation de chaînes avec +

En JavaScript, l'opérateur + a deux rôles :

- ➕ Addition (nombres)

- 🔗 Concaténation (chaînes)

```js
"Hello" + "World"       // "HelloWorld"
"1" + 2                 // "12"
2 + "1"                 // "21"
```

### ⚠️ Si l’un des deux est une chaîne, l’autre est converti en chaîne avant la concaténation !

### 🌀 Attention à l'ordre :

```js
2 + 2 + "1"     // "41" (car 2 + 2 = 4, puis "4" + "1")
"1" + 2 + 2     // "122" ("1" + "2" = "12", puis "12" + "2")
```

## 🧮 Précédence des opérateurs (ordre d’exécution)

📐 Les opérateurs ne sont pas tous exécutés dans l’ordre d’écriture !

Certains sont prioritaires (comme dans les maths).

|🔢 Priorité	|🧪 Opérateur	|🎯 Exemple
---	| ---	| ---
14	|+ x, - x (unaires)	|-5, +true
13	|**	|2 ** 3 = 8
12	|*, /, %	|6 / 2 * 3
11	|+, -	|5 + 3 - 2
2	|= (affectation)	|x = 2 + 2

### 👑 Les parenthèses ( ) sont toujours prioritaires :

```js
2 + 3 * 4     // 14 (3*4 = 12 → 2+12)
(2 + 3) * 4   // 20 (5 * 4)
```

## 📈📉 Préfixe et Postfixe (++ / --)

### 🔢 Incrémentation / Décrémentation :

- ++ ➕ ajoute 1

- -- ➖ enlève 1

### ✨ Préfixe : ++a ou --a

➡️ Ajoute/soustrait puis retourne la nouvelle valeur

let a = 1;
let b = ++a;     // a = 2, b = 2

### ⏪ Postfixe : a++ ou a--

➡️ Retourne l’ancienne valeur, puis incrémente/décrémente

let a = 1;
let b = a++;     // a = 2, b = 1

### ✅ Résumé :

| Forme	| Action	| Retourne |
| --- | --- | --- |
|++a	| Incrémente AVANT	| Nouvelle valeur |
|a++	| Incrémente APRÈS	| Ancienne valeur |

### 💡 Astuce : si tu n’utilises pas la valeur retournée, les deux sont équivalentes :

```js
i++;
++i;
// identiques si la valeur retournée n’est pas utilisée
```
