# 🔍 Comparaison en JavaScript

Les opérateurs de comparaison permettent de comparer des valeurs et retournent un résultat de type booléen (true ou false).
Opérateurs de comparaison de base :

## 1. Plus grand que :

a > b : Vérifie si a est strictement plus grand que b.

```js
Exemple : 5 > 3 → true
Exemple : 2 > 4 → false
Exemple : 'a' > 'b' → false (comparable lexicographiquement)
```

## 2. Plus petit que :

a < b : Vérifie si a est strictement plus petit que b.

```js
Exemple : 2 < 4 → true
Exemple : 10 < 5 → false
```

## 3. Plus grand ou égal à :

a >= b : Vérifie si a est plus grand ou égal à b.

```js
Exemple : 5 >= 5 → true
Exemple : 3 >= 4 → false
```

## 4. Plus petit ou égal à :

a <= b : Vérifie si a est plus petit ou égal à b.

```js
Exemple : 3 <= 5 → true
Exemple : 6 <= 4 → false
```

## 5. Égalité (non stricte) :

a == b : Compare a et b après une conversion de type si nécessaire.

```js
Exemple : '2' == 2 → true (la chaîne '2' est convertie en nombre).
Exemple : '0' == 0 → true (la chaîne '0' devient 0).
```

## 6. Non-égalité (non stricte) :

a != b : Compare a et b après une conversion de type.

```js
Exemple : '5' != 5 → false (les deux sont équivalents après conversion).
```

## 7. Égalité stricte :

a === b : Compare a et b sans conversion de type. Les deux doivent être du même type et de même valeur.

```js
Exemple : '2' === 2 → false (types différents : chaîne et nombre).
Exemple : 0 === false → false (types différents).
```

## 8. Non-égalité stricte :

a !== b : Compare a et b sans conversion de type.

```js
Exemple : '2' !== 2 → true (types différents).
Exemple : false !== 0 → true (types différents).
```

Comportement particulier des types :

## 9. Comparaison de chaînes de caractères :

Les chaînes sont comparées lexicographiquement (comme dans un dictionnaire).

```js
Exemple : 'Z' > 'A' → true
Exemple : 'Glow' > 'Glee' → true (comparaison caractère par caractère).
Exemple : 'Bee' > 'Be' → true (la chaîne 'Bee' est plus longue).
```

**Résumé :**

- Les chaînes sont comparées caractère par caractère selon leur code Unicode.

- Les majuscules sont toujours inférieures aux minuscules en raison de l'ordre Unicode.

- Si deux chaînes sont identiques jusqu'à un certain caractère mais ont une longueur différente, la chaîne la plus longue est plus grande.

## 10. Conversion de type (opérateurs non stricts) :

Lorsque des types différents sont comparés, JavaScript tente de les convertir en nombres.

```js
Exemple : '2' > 1 → true (la chaîne '2' devient le nombre 2).
Exemple : '01' == 1 → true (la chaîne '01' devient le nombre 1).
Exemple : true == 1 → true et false == 0 → true (les booléens sont convertis en nombres).
```

## 11. Comparaison avec null et undefined :

null et undefined ne sont pas égaux aux autres valeurs (à l'exception de la comparaison non stricte ==).

```js
null == undefined → true, mais null === undefined → false.
```

**Exemple :**

```js
null == undefined  // true
null === undefined // false
```

## 12. Comparaison null vs 0 :

```js
null > 0 → false
null == 0 → false
null >= 0 → true (la comparaison >= convertit null en 0).
```

**Exemple :**

```js
null > 0     // false
null == 0    // false
null >= 0    // true
```

## 13. Comparaison undefined :

```js
undefined > 0 → false
undefined < 0 → false
undefined == 0 → false
```

undefined est comparé avec NaN, qui est toujours faux pour toutes les comparaisons.

**Exemple :**

```js
undefined > 0   // false
undefined < 0   // false
undefined == 0  // false
```

## 14. Précautions à prendre :

Ne comparez pas directement null ou undefined avec d'autres valeurs à l'aide de <, >, <=, >=. Utilisez une vérification séparée pour ces valeurs.

```js
if (variable == null) { // vérifie si variable est null ou undefined
    console.log("La variable est null ou undefined");
}
```

Égalité stricte pour éviter les erreurs :
Utilisez === (égalité stricte) pour éviter les erreurs liées aux conversions implicites de type. Cela permet de comparer à la fois la valeur et le type.

**Exemples concrets :**

## 15. Comparaison avec un nombre :

```js
console.log('10' == 10); // true, la chaîne '10' est convertie en nombre
console.log('10' === 10); // false, types différents
```

## 16. Comparaison avec null et undefined :

```js
console.log(null == undefined); // true, spécialité de == (égalité non stricte)
console.log(null === undefined); // false, car les types sont différents
console.log(null > 0); // false
console.log(undefined > 0); // false
```

## 17. Points clés à retenir :

`==` : effectue une conversion de type.

`===` : compare sans conversion de type (recommandé pour éviter des erreurs).

Les chaînes sont comparées lexicographiquement (caractère par caractère).

`null` et `undefined` sont traités de manière particulière :

`null` == `undefined` → `true`

`null` === `undefined` → `false`

Evitez les comparaisons avec null et undefined sans les vérifier au préalable.

---


### 18. Opérateurs de comparaison :

Les opérateurs <, >, <= et >= sont des opérateurs de comparaison en JavaScript. Ils servent à comparer deux valeurs et à déterminer leur relation par rapport à l'une à l'autre. Tous ces opérateurs renvoient un résultat booléen (soit true soit false), en fonction de la comparaison effectuée.

**Résumé :**

- < : Vérifie si une valeur est inférieure à une autre.

- > : Vérifie si une valeur est supérieure à une autre.

- <= : Vérifie si une valeur est inférieure ou égale à une autre.

- >= : Vérifie si une valeur est supérieure ou égale à une autre.

Ces opérateurs sont utiles pour effectuer des comparaisons numériques ou même pour comparer des chaînes de caractères en fonction de leur ordre lexicographique (comme dans un dictionnaire).

