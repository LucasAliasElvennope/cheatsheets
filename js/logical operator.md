# Opérateurs logiques

Il y a trois opérateurs logiques en JavaScript : || (OR), && (AND), ! (NOT), ?? (Coalescence des nulles). Nous couvrons ici les trois premiers, l’opérateur ?? est dans l’article suivant.

Bien qu’ils soient appelés “logiques”, ils peuvent être appliqués à des valeurs de tout type, pas seulement booléennes. Le résultat peut également être de tout type.

Voyons les détails.

---
## 🔶 L’opérateur logique || (OR)

L’opérateur OR se note avec deux barres verticales : ||
C’est ce qu’on appelle un opérateur logique, et il permet de vérifier si au moins une condition est vraie.

### 🧪 Syntaxe :

```js
result = a || b;
```

### Cela signifie :

➡️ Si a est vrai, retourne a
➡️ Sinon, retourne b

### 🧠 Interprétation "classique"

Dans la logique booléenne traditionnelle (vrai ou faux), l’opérateur || fonctionne ainsi :

- true || true → ✅ true

- false || true → ✅ true

- true || false → ✅ true

- false || false → ❌ false

```js
alert(true  || true);   // true
alert(false || true);   // true
alert(true  || false);  // true
alert(false || false);  // false
```

🧠 Ici, le résultat est true dès qu’il y a au moins un true.

### 🧾 Exemple simple avec un if :

```js
let hour = 9;

if (hour < 10 || hour > 18) {
  alert("Le bureau est fermé.");
}
```

➡️ Ici, le message s’affiche si l’heure est avant 10h ou après 18h.
Suffit qu’une des deux conditions soit vraie pour que ça passe ✅

### 🔁 Plusieurs conditions avec OR :

```js
let hour = 12;
let isWeekend = true;

if (hour < 10 || hour > 18 || isWeekend) {
  alert("Le bureau est fermé.");
}
```

➡️ Même si l’heure est "normale", comme isWeekend est true, alors le message s’affiche.
Car une seule condition suffit à valider le OR.

### 🌟 Ce qui rend OR || puissant en JavaScript

Contrairement à d’autres langages où || ne sert qu’à faire du "vrai/faux", JavaScript va plus loin :
🔍 Il retourne la première valeur vraie (non convertie) trouvée dans une série d’expressions.

### 🧠 Règles précises du comportement de || :

- Il évalue les expressions de gauche à droite

- Il convertit chaque valeur en booléen pour vérifier si elle est "vraie" (truthy)

- Si une valeur est "truthy", il renvoie cette valeur originale et s’arrête immédiatement

- Si toutes les valeurs sont "falsy", il retourne la dernière valeur

### 📌 Exemples pratiques :

```js
alert(1 || 0); // 1 → 1 est la première valeur "vraie"
alert(null || 1); // 1 → car null est faux, mais 1 est vrai
alert(null || 0 || 1); // 1 → 0 est faux, mais 1 est vrai
alert(undefined || null || 0); // 0 → toutes fausses, renvoie la dernière
```

### 💡 Les valeurs "falsy" en JavaScript sont :

```js
false, 0, "" (chaîne vide), null, undefined, NaN
```

### 🎯 Cas concret : choisir une valeur disponible parmi plusieurs

Supposons que tu aies plusieurs variables, mais tu veux afficher la première qui a une vraie valeur :

```js
let firstName = "";
let lastName = "";
let nickName = "SuperCoder";

alert(firstName || lastName || nickName || "Anonymous");
```

### 🧠 Ici :

- firstName est vide → ❌

- lastName est vide → ❌

- nickName a une vraie valeur → ✅ affiché !

Si toutes étaient vides → affichage de "Anonymous" par défaut.

⚡ Comportement de court-circuit de ||

Encore une astuce puissante de l’opérateur OR en JavaScript : le court-circuit.
🔄 Qu’est-ce que ça veut dire ?

➡️ Dès qu’il trouve une valeur "vraie", il arrête immédiatement d’évaluer le reste.
🧪 Exemple :

true || alert("Pas affiché");
false || alert("Affiché !");

- Dans le premier cas, true est suffisant → alert n’est même pas exécuté

- Dans le second cas, false oblige à regarder à droite → alert s’exécute

🧠 C’est pratique pour exécuter du code uniquement si une condition est fausse.

### 📦 Résumé visuel :
a	b	a || b
true	true	✅ true
false	true	✅ true
true	false	✅ true
false	false	❌ false

Mais en JavaScript, || retourne la première valeur "vraie" :

"Hello" || 0        // "Hello"
null || "Salut"     // "Salut"
"" || "Texte"       // "Texte"
undefined || false  // false

---

### 🧩 Qu’est-ce que l’opérateur && (AND) en JavaScript ?

L’opérateur logique AND s’écrit avec deux esperluettes : &&.
Il permet de combiner deux conditions (ou plus) dans une expression logique.

Sa fonction principale est la suivante :

**👉 Il retourne true seulement si toutes les conditions sont vraies.**
**Si au moins une des conditions est fausse, alors le résultat est false.**

### 🧪 Syntaxe de base :

```js
result = a && b;
```

### 🔍 Comparaison simple avec des booléens :

```js
alert(true  && true);   // ✅ true
alert(false && true);   // ❌ false
alert(true  && false);  // ❌ false
alert(false && false);  // ❌ false
```

➡️ On voit que && ne renvoie true que si les deux côtés sont true.

### 🧠 Petite analogie :

Imagine que tu veux ouvrir une porte avec deux clés :

- Si tu as les deux clés, la porte s’ouvre. ✅

- Si une seule des deux clés est absente, impossible d’ouvrir. ❌

C’est exactement ce que fait && :
Il ne te donne un résultat true que si toutes les conditions sont remplies.

###     🧾 Exemple concret dans un if :

```js
let hour = 12;
let minute = 30;

if (hour == 12 && minute == 30) {
  alert("Il est 12h30 !");
}
```

### 🧠 Ici, JavaScript vérifie deux choses :

- Est-ce que hour vaut 12 ? ✅

- Est-ce que minute vaut 30 ? ✅

**👉 Les deux sont vraies, donc le message s’affiche 🎉**

🔁 Comme avec ||, on peut utiliser n’importe quel type de valeur, pas seulement true ou false.

### Par exemple :

```js
if (1 && 0) {
  alert("Ceci ne s’affichera pas.");
}
```

### Pourquoi ?

➡️ Car 1 est une valeur "truthy" (considérée comme vraie), mais 0 est "falsy" (faux).
Donc c’est comme faire :

```js
if (true && false) // ❌ false → ne passe pas
```

### 📦 Résumé visuel :

| Valeur de gauche | Valeur de droite | Résultat && |
| --- | --- | --- |
| true | true | ✅ true |
| true | false | ❌ false |
| false | true | ❌ false |
| false | false | ❌ false |

---

## 🔶 AND && — Recherche de la première valeur "fausse"

L’opérateur logique ET (AND) est représenté par deux esperluettes : &&

Il est généralement utilisé pour vérifier que toutes les conditions sont vraies.

Mais en JavaScript, il a un comportement plus complexe et puissant que dans les langages strictement booléens 💪.

🔁 Que se passe-t-il quand on enchaîne plusieurs valeurs avec && ?

### Syntaxe :

```js
result = value1 && value2 && value3;
```

### 🧠 Ce que fait JavaScript (étapes) :

1. Il évalue chaque valeur de gauche à droite.

2. À chaque étape, il convertit la valeur en booléen (true/false) pour voir si elle est "truthy" ou "falsy".

3. 🔍 Si une valeur est "falsy", il s'arrête immédiatement et retourne cette valeur d'origine.

4. ✅ Si toutes les valeurs sont "truthy", alors il renvoie la dernière valeur.

### 🟡 En d'autres termes :

- && renvoie la première valeur "fausse"

- Sinon, il renvoie la dernière vraie

### 📌 Rappel des valeurs falsy :

Les valeurs suivantes sont considérées comme "fausses" (falsy) en JavaScript :

- false

- 0

- "" (chaîne vide)

- null

- undefined

- NaN

Toutes les autres sont "truthy" (considérées comme vraies).

### 🔍 Exemples concrets :

### 1️⃣ Une vraie suivie d’une fausse :

```js
alert(1 && 0); // 0
```

- 1 est vrai (truthy)

- 0 est faux (falsy) → donc renvoyé immédiatement

### 2️⃣ Deux vraies valeurs :

```js
alert(1 && 5); // 5
```

- 1 est vrai ✅ → passe

- 5 est vrai ✅ → donc renvoyé (la dernière valeur)

### 3️⃣ Une valeur fausse dès le début :

```js
alert(null && 5); // null
```

- null est falsy ❌ → retour immédiat, même pas besoin d’évaluer 5

### 🧪 Autres cas avec plusieurs valeurs :

```js
alert(1 && 2 && null && 3); // null
```

- 1 → ✅ (truthy)

- 2 → ✅ (truthy)

- null → ❌ → retourne null immédiatement

- 3 ne sera jamais évalué

➡️ On dit ici que l'évaluation est "court-circuitée" dès qu'une valeur fausse est rencontrée. ⚡

### ✅ Quand toutes les valeurs sont vraies :

```js
alert(1 && 2 && 3); // 3
```

- 1 → ✅

- 2 → ✅

- 3 → ✅

🟢 Aucune valeur fausse ➜ JavaScript retourne la dernière valeur

### 🧠 Résumé visuel :

| Expression | Résultat renvoyé | Explication |
| --- | --- | --- |
| true && true | true | Tout est vrai |
| true && false | false | Faux trouvé → retourne false |
| 1 && 0 | 0 | 0 est falsy |
| null && 5 | null | null est falsy |
| 1 && 2 && 3 | 3 | Toutes les valeurs sont truthy |
| 1 && 2 && null && 3 | null | null est la première fausse |

### ⚡ Court-circuit : un super pouvoir 💥

Le comportement de court-circuit est utile quand on veut exécuter une expression uniquement si toutes les précédentes sont vraies :

```js
true && alert("Ceci s'affiche"); // ✅ s’affiche
false && alert("Ceci ne s'affiche pas"); // ❌ ignoré
```

➡️ Dans la deuxième ligne, false arrête tout : alert() ne sera jamais appelé !

### 🧩 Utilisation typique dans le code :

Imaginons que tu veuilles afficher un message uniquement si un utilisateur est connecté ET que son rôle est admin :

```js
if (isLoggedIn && isAdmin) {
  alert("Bienvenue, administrateur !");
}
```

Si l’un des deux est faux → pas de message.

---

## ❗ L’opérateur logique NOT (!) — Inverser la vérité

En JavaScript, l’opérateur logique NOT (non) est représenté par un point d’exclamation !.
Il permet d’inverser une valeur booléenne : il transforme true en false et inversement.

### 🧱 Syntaxe simple :

```js
result = !value;
```

🧠 L’opérateur ! agit en deux étapes :

    Il convertit la valeur en un booléen (true ou false), même si ce n’était pas un booléen au départ.

    Il inverse ce booléen.

### 🔍 Exemples de base :

```js
alert( !true ); // false
alert( !false ); // true
alert( !0 ); // true (car 0 est "falsy")
alert( !"Bonjour" ); // false (car "Bonjour" est "truthy")
alert( !null ); // true (car null est "falsy")
```

### Donc :

| Valeur | Convertie en booléen | !valeur renvoie |
| --- | --- | --- |
| true | true | false |
| false | false | true |
| 0 | false | true |
| "Bonjour" | true | false |
| null | false | true |
| undefined | false | true |
| [] (tableau vide) | true | false |

### 🔁 Double NOT !! — Convertir une valeur en vrai booléen

Tu peux utiliser deux fois le ! de suite, comme ceci : !!valeur.

C’est une astuce courante pour convertir n’importe quelle valeur en un booléen (true ou false) sans inverser le résultat final.
✨ Pourquoi ça marche ?

- Le premier ! transforme la valeur en booléen, puis l’inverse.

- Le second ! inverse à nouveau le résultat.

- Résultat : tu obtiens une conversion propre en booléen.

### 🧪 Exemples :

```js
alert( !!"hello" ); // true — car une chaîne non vide est truthy
alert( !!0 );       // false — car 0 est falsy
alert( !!null );    // false
alert( !!123 );     // true
```

### 🔁 Alternative : Boolean(valeur)

Tu peux aussi utiliser la fonction intégrée Boolean() pour convertir une valeur en booléen :

```js
Boolean("Salut"); // true
Boolean(0);       // false
```

**🟢 Résultat identique à !!valeur, mais plus explicite, parfois préféré pour la lisibilité.**

**⚠️ Précédence de ! : la plus élevée des opérateurs logiques**

👉 L'opérateur ! est prioritaire sur tous les autres opérateurs logiques.
Cela signifie qu’il est toujours évalué en premier, même avant && ou ||.

### Exemple :

```js
let result = !true && true;
alert(result); // false
```

### 🔁 Alternative : Boolean(valeur)

Tu peux aussi utiliser la fonction intégrée Boolean() pour convertir une valeur en booléen :

Boolean("Salut"); // true
Boolean(0);       // false

**🟢 Résultat identique à !!valeur, mais plus explicite, parfois préféré pour la lisibilité.**

**⚠️ Précédence de ! : la plus élevée des opérateurs logiques**

👉 L'opérateur ! est prioritaire sur tous les autres opérateurs logiques.
Cela signifie qu’il est toujours évalué en premier, même avant && ou ||.

### Exemple :

```js
let result = !true && true;
alert(result); // false
```

**Ici, !true est évalué en premier, ce qui donne false && true → donc false.**

### 🧩 Utilisation typique :

Tu veux faire quelque chose uniquement si une condition est fausse ? Utilise ! :

```js
let isLoggedIn = false;

if (!isLoggedIn) {
  alert("Tu dois te connecter !");
}
```

### ✅ Résumé visuel :

| Expression | Résultat |
| --- | --- |
| !true | false |
| !false | true |
| !0 | true |
| !!"hello" | true |
| Boolean(null) | false |
| !!undefined | false |
| ![] | false |

---

## 🤷‍♂️ L’opérateur de coalescence des nuls ?? (Nullish Coalescing)

L’opérateur ?? permet de retourner une valeur par défaut uniquement lorsque la variable est null ou undefined.
C’est une alternative plus précise que ||, qui est parfois trop agressif.

### 🧠 Pourquoi utiliser ?? ?

JavaScript a beaucoup de valeurs considérées comme "falsy" :

- false

- 0

- "" (chaîne vide)

- null

- undefined

- NaN

L’opérateur || ignore toutes ces valeurs et saute directement à la suivante.
Mais parfois, on veut garder 0, false ou une chaîne vide comme valeurs valides !

C’est là que ?? devient très utile 👍

### 📌 Syntaxe :

```js
let result = a ?? b;
```

👉 Si a est défini (≠ null ou undefined), alors result = a

👉 Sinon, result = b

### 📙 Exemple 1 – Basique :

let user;

alert(user ?? "Anonyme"); // "Anonyme", car user = undefined

user = "Lucas";
alert(user ?? "Anonyme"); // "Lucas"

➡️ Très pratique pour afficher une valeur de secours quand une variable n’est pas définie.

### 💡 Exemple 2 – Plusieurs alternatives :

```js
let prenom = null;
let pseudo = null;
let surnom = "CodeurFou";

let nomAffiche = prenom ?? pseudo ?? surnom ?? "Anonyme";

alert(nomAffiche); // "CodeurFou"
```

➡️ On cherche la première valeur définie 🧩 dans une série de variables.

### 🔁 Comparaison avec ||

⚠️ Attention : || vérifie si la valeur est "falsy", pas juste null ou undefined.


### 🔁 Comparaison entre || et ?? :

- 0 || 100 → 100 ❌
- 0 ?? 100 → 0 ✅

👉 0 est considéré comme falsy, donc ignoré par ||, mais ?? le garde car ce n’est pas null/undefined

- "" || "default" → "default" ❌
- "" ?? "default" → "" ✅

👉 Une chaîne vide est aussi falsy pour ||, mais pas pour ??

- false || true → true ❌
- false ?? true → false ✅

👉 false est falsy, donc ignoré par ||, mais ?? le considère comme défini

- null || "valeur" → "valeur" ✅
- null ?? "valeur" → "valeur" ✅

👉 null est considéré comme non défini par les deux opérateurs

- undefined || "valeur" → "valeur" ✅
- undefined ?? "valeur" → "valeur" ✅

👉 undefined est aussi non défini pour les deux



### ⚙️ Exemple parlant :

```js
let hauteur = 0;

alert(hauteur || 100); // 100 ❌ (0 est "falsy")
alert(hauteur ?? 100); // 0 ✅ (0 est défini, donc conservé)
```

➡️ 0 est une valeur parfaitement valide pour une hauteur ! ?? respecte ça ✅

---

## 🧮 Priorité des opérateurs

L’opérateur ?? a une priorité faible :

- Il est évalué après les opérateurs comme +, *, etc.

- Il est évalué avant =, ? :, etc.

**⚠️ Donc utilise des parenthèses pour éviter des erreurs de logique :**

```js
let hauteur = null;
let largeur = null;

let surface = (hauteur ?? 100) * (largeur ?? 50); // ✅ 5000
```

❌ Mauvais exemple (sans parenthèses) :

```js
let surface = hauteur ?? 100 * largeur ?? 50;
```

Ce code est lu comme :

```js
let surface = hauteur ?? (100 * largeur) ?? 50;
```

➡️ Ce n’est pas ce qu’on voulait 😵

### 🚫 Interdit avec || ou && sans parenthèses

JavaScript interdit d’utiliser ?? directement avec || ou && sans parenthèses :

```js
let x = 1 && 2 ?? 3; // ❌ Erreur de syntaxe
```

✅ Pour corriger :

```js
let x = (1 && 2) ?? 3; // ✅ Résultat : 2
```

✅ Résumé final

| Point clé | Détail |
| --- | --- |
| Utilité | Donner une valeur par défaut quand une variable est null ou undefined |
| Différence vs ` | Garde les valeurs valides même si elles sont "falsy" (false, 0, "") |
| Priorité | Basse : utilise des parenthèses pour éviter les bugs |
| Syntaxe sûre | ⚠️ Jamais mélanger directement ?? avec || ou && sans parenthèses |