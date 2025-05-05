# ❓ C'est quoi une comparaison en JavaScript ?

Une comparaison permet de comparer deux valeurs (nombres, chaînes, booléens…) pour savoir si une condition est vraie ou fausse ✅❌

➡️ Le résultat d'une comparaison est toujours un booléen : true (vrai) ou false (faux)

### 🧪 Exemple :

```js
5 > 3       // true → 5 est plus grand que 3
2 == '2'    // true → les valeurs sont égales (mais pas les types)
"chat" < "zèbre"  // true → ordre alphabétique
```

### 🗣️ En gros, une comparaison permet à ton programme de prendre des décisions :

"Si cette condition est vraie, alors je fais ça… sinon je fais autre chose."

### 🧮 Comparaisons en JavaScript

#### 🎯 Opérateurs de base

| Opérateur	Signification	Exemple	Résultat |
| --- | --- | --- | --- |
| >	Plus grand que	3 > 2	true |
| <	Plus petit que	1 < 2	true |
| >=	Supérieur ou égal	2 >= 2	true |
| <=	Inférieur ou égal	1 <= 0	false |
| ==	Égalité (valeurs)	'2' == 2	true ⚠️ (conversion automatique) |
| ===	Égalité stricte	'2' === 2	false ✅ |
| !=	Différent (valeurs)	'2' != 2	false ⚠️ |
| !==	Différent strictement	'2' !== 2	true ✅ |

🧠 Résultat = booléen

Toutes les comparaisons donnent true ✅ ou false ❌

```js
alert(5 > 2);      // true
let res = 3 == 4;
console.log(res);  // false
```

### 📚 Comparaison de chaînes

Les chaînes sont comparées lettre par lettre 🅰️➡️🧾 (ordre lexicographique)

```js
'Z' > 'A'     // true
'Glow' > 'Glee' // true → o > e
'Bee' > 'Be'  // true → plus longue
```

### ⚠️ Majuscules < Minuscules (selon l’Unicode)

### 🔁 Comparaison de types différents

JavaScript convertit en nombres si les types sont différents 🔢

```js
'2' > 1     // true → '2' devient 2
'01' == 1   // true → '01' devient 1
true == 1   // true
false == 0  // true
```

😵 Attention : piégeux !

```js
let a = 0;
let b = "0";

Boolean(a);       // false
Boolean(b);       // true
a == b;           // true 😱
```

➡️ Pourquoi ? == convertit les types, mais Boolean() suit d’autres règles
🛡️ Égalité stricte recommandée

Utilise === pour éviter les conversions surprises :

```js
0 == false       // true ❌
0 === false      // false ✅
'' == false      // true ❌
'' === false     // false ✅
```

### 🧨 null & undefined

| Comparaison	Résultat	Pourquoi ? |
| --- | --- | --- |
| null == undefined	true ✅	exception spéciale |
| null === undefined	false ❌	types différents |
| null > 0	false ❌	null devient 0 |
| null >= 0	true 😵	null → 0 donc égal ou plus grand |
| undefined == 0	false ❌	undefined n’est égal qu’à null |
| undefined > 0	false ❌	undefined devient NaN |


### ✅ Conseils importants

- Utilise === pour les comparaisons d’égalité ✅
- Évite de comparer null/undefined avec <, >, <=, >= ⚠️
- Vérifie séparément si une valeur est null ou undefined 🧪

```js
if (val != null && val > 0) {
  // OK !
}
```

