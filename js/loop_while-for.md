# 🔁 Les boucles en JavaScript

👉 Répéter une action plusieurs fois ? Utilise une boucle !

## 🌀 Pourquoi utiliser une boucle ?

👉 Parfois, on veut répéter une action plusieurs fois :

- Parcourir une liste 📦📦📦

- Afficher les nombres de 1 à 10 🔢

- Refaire une opération tant qu'une condition est vraie ✅

## ***🧮 Les types de boucles***

## 🧷 `while` – Tant que la condition est vraie

```js
while (condition) {
  // corps de la boucle
}
```


### **🧠 Comment ça marche ?**

- La condition est testée ➕

- Si elle est true, on exécute le code à l'intérieur

- Puis on revient au test ➰

### **🧪 Exemple :**

```js
let i = 0;
while (i < 3) {
  alert(i); // Affiche : 0, 1, 2
  i++;
}
```

### **🌀 Résumé :**

- 🔁 Une itération est une exécution du corps d'une boucle.

- ⏳ Si on oublie i++, la boucle tourne indéfiniment (⚠️ boucle infinie).

- ✅ while accepte n’importe quelle expression comme condition : elle est automatiquement convertie en booléen (vrai/faux).

- ✂️ Par exemple : while (i) est équivalent à while (i != 0).

_ 📍 Une itération = 1 tour de boucle

***⚠️ Attention à ne pas oublier `i++` sinon ➡️ boucle infinie 🔁🔁🔁***

## ✅ `do...while` – Exécute au moins une fois

```js
do {
  // corps
} while (condition);
```

### 🧠 Différence avec `while` ?

- Le corps s’exécute d’abord une fois 📦

- Ensuite on teste la condition

### **🧪 Exemple :**

```js
let i = 0;
do {
  alert(i); // Affiche : 0, 1, 2
  i++;
} while (i < 3);
```
Cette forme de syntaxe est rarement utilisée, sauf lorsque vous souhaitez que le corps de la boucle s’exécute au moins une fois, quelle que soit la condition. Habituellement, l’autre forme est préférée : while(…) {…}.

***📌 Utile quand tu veux exécuter le code au moins une fois, même si la condition est fausse.***

## 📊 `for` – La plus utilisée 💪

### 🔁 La boucle for est la plus utilisée car elle est compacte et puissante.

### **🧱 Elle se compose de 3 parties :**
```js
for (début; condition; étape) {
  // corps de la boucle
}
```

### ***🔍 Exemple :***

```js
for (let i = 0; i < 3; i++) {
  alert(i); // Affiche 0, puis 1, puis 2
}
```

### **🧩 Décomposition :**

- Début → let i = 0 : exécuté une seule fois au début

- Condition → i < 3 : testée avant chaque itération

- Corps → alert(i) : exécuté si la condition est vraie

- Étape → i++ : exécuté après chaque corps

### **🔄 L’ordre d’exécution :**

- début

- vérifier condition

- exécuter corps

- exécuter étape

- retour à la condition…

### **📋 Résultat pas à pas pour for (let i = 0; i < 3; i++) :**

- i = 0 → ✅ condition → affiche 0 → i++

- i = 1 → ✅ condition → affiche 1 → i++

- i = 2 → ✅ condition → affiche 2 → i++

- i = 3 → ❌ condition → boucle terminée

## **🔄 Boucle for : On peut omettre certaines parties !**

La boucle for classique est structurée comme ça :

```js
for (début; condition; étape) {
  // ... instructions ...
}
```

Mais en réalité, chaque partie est optionnelle (oui oui ! 😮). On peut donc écrire des for plus courts selon nos besoins, tant qu’on garde les deux ;.

### ✅ 1. Omettre le début (début)

**📌 Si tu as déjà initialisé ta variable avant, pas besoin de le refaire dans la boucle.**

```js
let i = 0; // Déjà initialisé

for (; i < 3; i++) {
  alert(i); // Affiche 0, 1, 2
}
```

🧠 Ici, on saute juste l’étape d’initialisation dans la boucle car elle est déjà faite avant.

### ✅ 2. Omettre l’étape (étape)

**📌 Tu peux faire l’incrémentation (ou autre étape) directement dans le corps de la boucle.**

```js
let i = 0;

for (; i < 3;) {
  alert(i); // Affiche 0, 1, 2
  i++;      // Incrémentation manuelle
}
```

🟰 Cela revient exactement à écrire une boucle while (i < 3), car tu gères toi-même ce qui se passe à chaque tour.

### ✅ 3. Omettre les deux : début ET étape

```js
let i = 0;

for (; i < 3;) {
  alert(i++);
}
```
📍 On a juste une condition, le reste est géré dans le corps.

### 🔁 4. Tout omettre = Boucle infinie !

```js
for (;;) {
  // Cette boucle tourne sans fin 😵‍💫
}
```

🧠 C’est une boucle sans condition d’arrêt → idéale pour des programmes qui doivent tourner en continu jusqu’à un break ou une erreur.

***⚠️ ATTENTION : Les ; sont OBLIGATOIRES ❗***

Même si tu omets certaines parties, les deux points-virgules doivent toujours être là, sinon tu auras une erreur de syntaxe.

## Briser une boucle avec break

Une boucle s'arrête normalement quand sa condition devient fausse. Mais on peut forcer l'arrêt de la boucle à tout moment avec la directive break.

### ***✅ Exemple avec break :***

```js
let sum = 0;

while (true) {

  let value = +prompt("Entrez un nombre", '');

  if (!value) break; // (*) Si la valeur est vide ou nulle, briser la boucle

  sum += value;

}
alert('Sum: ' + sum);
```

### 🧠 Explication détaillée :

- Boucle infinie (while (true)) :

- Cette boucle est infinie parce que la condition true est toujours vraie. Elle doit donc être brisée manuellement.

- Demande de saisie utilisateur :

- Le programme demande à l'utilisateur d'entrer un nombre via la fonction prompt.

- Condition de sortie avec break :

- Si l'utilisateur entre une valeur vide ou annule l'entrée, la condition !value devient vraie et la directive break est exécutée, ce qui arrête immédiatement la boucle.

- Accumulation des valeurs :

- Tant que l'utilisateur entre des chiffres, ils sont ajoutés à la variable sum.

### 💡 Pourquoi utiliser break ?

La combinaison "boucle infinie + break" est idéale pour des situations où vous devez vérifier une condition non seulement au début ou à la fin de la boucle, mais aussi en plein milieu de l'exécution, voire à plusieurs endroits dans le corps de la boucle.

### ⚠️ Important à retenir :

- break arrête immédiatement l'exécution de la boucle et passe à la ligne suivante après la boucle.

- Utilisez break avec prudence, car il peut rendre le code moins lisible s'il est mal utilisé.

## 🏷️ Les labels pour contrôler les boucles imbriquées

Quand tu as des boucles dans des boucles, un break ou continue normal n’affecte que la boucle en cours.

Mais parfois, tu veux quitter plusieurs boucles d’un coup... ➡️ les labels sont là pour ça !

### 📍 Définir un label :

Un label, c’est un nom suivi de : juste avant une boucle :

```js
monLabel: for (...) {
  ...
}
```

Ensuite, tu peux utiliser break monLabel pour quitter la boucle étiquetée, même si tu es à l’intérieur d’une autre boucle plus profonde.

### ✅ Exemple pratique avec break et un label :

```js
outer: for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    let input = prompt(`Valeur à (${i},${j})`, '');

    if (!input) break outer; // 🛑 Quitte TOUTES les boucles

    // Sinon, on continue...
  }
}

alert("Fini !");
```

🧠 Ici, si l’utilisateur annule ou laisse vide → on quitte les deux boucles d’un coup grâce à break outer.

### 🔁 On peut aussi faire continue vers une boucle étiquetée :

```js
externe: for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    if (i + j > 3) continue externe; // 🔁 Reprend l'itération de la boucle externe
    alert(`i=${i}, j=${j}`);
  }

}
```

### 📌 Utilisation rare mais puissante quand on veut contrôler précisément le flux des boucles imbriquées.

### ***⚠️ Attention : on ne peut pas sauter "n'importe où" !***

```js
break monLabel; // ❌ Interdit ici si on n’est pas dans le bloc étiqueté

monLabel: for (...) { ... }
```

- 🔸 break ou continue doivent être dans une boucle ou un bloc étiqueté
- 🔸 Ils ne servent que pour contrôler le flux, pas pour “sauter” partout dans le code

### 📝 À retenir :

- ✅ break label → quitte la boucle labellisée

- ✅ continue label → passe à l’itération suivante de la boucle labellisée

- ❌ On ne peut pas “sauter” dans le code avec un label

### 📝 Résumé :

Il existe trois types principaux de boucles en JavaScript :

- while : La condition est vérifiée avant chaque itération. Si la condition est fausse dès le départ, le corps de la boucle ne sera jamais exécuté.

### Exemple :

```js
while (condition) {
  // Corps de la boucle
}
```

do..while : La condition est vérifiée après chaque itération. Le corps de la boucle sera donc exécuté au moins une fois, même si la condition est fausse dès le départ.

### Exemple :

```js
do {
  // Corps de la boucle
} while (condition);
```

for : La condition est vérifiée avant chaque itération, mais cette boucle permet de spécifier des paramètres supplémentaires (initialisation, condition, étape) de manière concise.

### Exemple :

```js
for (let i = 0; i < 5; i++) {
  // Corps de la boucle
}
```

### Boucles infinies :

Une boucle infinie est une boucle qui ne s'arrête jamais tant que la condition reste vraie. On peut en créer une avec while(true) et la stopper avec la directive break.

### Exemple de boucle infinie :

```js
while (true) {
  // Corps de la boucle
  if (condition) break; // Sortir de la boucle si condition est vraie
}
```

### continue :

La directive continue permet de passer à l'itération suivante de la boucle, en sautant le reste du code dans l'itération en cours. Elle est souvent utilisée pour ignorer certaines itérations.

### Exemple avec continue :

```js
for (let i = 0; i < 5; i++) {
  if (i % 2 === 0) continue; // Ignore les valeurs paires
  console.log(i); // Affiche uniquement les valeurs impaires
}
```

### Labels avec break et continue :

Les labels permettent de sortir de boucles imbriquées ou de sauter directement à une itération spécifique dans une boucle imbriquée. Un label est un identifiant suivi de deux points (par exemple labelName:). Les directives break et continue peuvent être utilisées avec un label pour contrôler plus précisément le flux des boucles imbriquées.

### Exemple avec label :

```js
outer: for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    if (condition) break outer; // Sortir de la boucle "outer"
  }
}
```

### En résumé :

- while et do..while vérifient la condition à des moments différents.

- for est plus flexible et concis pour des boucles avec des étapes définies.

- continue permet de passer à l'itération suivante.

- break et continue peuvent utiliser des labels pour sortir des boucles imbriquées.