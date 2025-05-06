# 🌿 Les branches conditionnelles : if, ?

En JavaScript, il arrive souvent qu’on doive exécuter du code seulement si une condition est remplie (par exemple : si un utilisateur est majeur ou non).
Pour cela, on utilise deux grands outils :

- `if` ➡️ exécuter un bloc de code si une condition est vraie

- `?` (opérateur ternaire) ➡️ choisir rapidement entre deux valeurs selon une condition

## 🔍 if (...) : tester une condition

```js
if (condition) {
  // code à exécuter si la condition est vraie ✅
}
```

### 🧠 Exemple simple :

```js
let year = prompt("En quelle année ECMAScript 2015 est sorti ?");

if (year == 2015) {
  alert("Tu as raison ! 🎉");
}

else {
  alert("Dommage ❌");
}
```

📌 Ici, year == 2015 est la condition.

Si elle est vraie (true), alors le bloc à l’intérieur de { ... } est exécuté.

Si elle est fausse (false), le bloc est ignoré.


## 🧱 Plusieurs instructions ? Toujours des {} !

Si tu veux exécuter plusieurs lignes à l’intérieur du if, utilise toujours des accolades `{}` :

```js
if (year == 2015) {
  alert("C'est exact ✅");
  alert("Tu es trop fort ! 💪");
}
```

👀 Même s’il n’y a qu’une seule ligne, il est recommandé de toujours utiliser les {} pour éviter les bugs et améliorer la lisibilité.

---

## 🧮 Conversion booléenne automatique

JavaScript évalue la condition à l’intérieur du if (...) et la convertit en true ou false.

**💡 Rappel** : certaines valeurs sont automatiquement considérées comme "fausses" (falsy) et d’autres comme "vraies" (truthy).

| ❌ Falsy	| ✅ Truthy	|
| --- | --- |
| 0	| tout nombre ≠ 0 |
| "" (chaîne vide)	| chaîne non vide |
| null	| undefined	|
| NaN	|

### 🧪 Exemple :

```js
if (0) {
  // ❌ ne sera jamais exécuté
}

if (1) {
  // ✅ sera exécuté
}
```

### Ou encore :

```js
let cond = (year == 2015); // renvoie true ou false

if (cond) {
  alert("Bonne réponse !");
}
```

## 🔀 else : si la condition est fausse

Tu peux ajouter un bloc else pour exécuter du code quand la condition est fausse :

### 🧠 Exemple :

```js
if (year == 2015) {
  alert("Bonne réponse ✅");
} else {
  alert("Dommage ❌");
}
```

## 🔀 else if : plusieurs conditions

Tu veux tester plusieurs cas différents ? Utilise else if :

```js
let year = prompt("En quelle année ECMAScript-2015 est sorti ?");

if (year < 2015) {
  alert("Trop tôt ⏰");
} else if (year > 2015) {
  alert("Trop tard 🕰️");
} else {
  alert("Exactement 🎯");
}
```

**👉 JavaScript vérifie les conditions dans l’ordre. Il s’arrête dès qu’une est vraie.**

Tu peux enchaîner autant de else if que tu veux. Le else final est optionnel, mais souvent utile. 

## Opérateur ternaire ‘?’

Parfois, nous devons attribuer une variable en fonction d’une condition.

### Exemple :

```js
let accessAllowed;
let age = prompt('How old are you?', '');

if (age > 18) {
  accessAllowed = true;
} else {
  accessAllowed = false;
}

alert(accessAllowed);
```

L’opérateur dit “ternaire” ou “point d’interrogation” nous permet de le faire plus rapidement et plus simplement.

L’opérateur est représenté par un point d’interrogation ?. Appelé aussi “ternaire” parce que l’opérateur a trois opérandes. C’est en fait le seul et unique opérateur en JavaScript qui en a autant.

La syntaxe est :

```js
let result = condition ? value1 : value2
```

La condition est évaluée, si elle est vraie, alors value1 est retournée, sinon – value2.

### Exemple :

```js
let accessAllowed = (age > 18) ? true : false;
```

Techniquement, nous pouvons omettre les parenthèses autour de age > 18. L’opérateur point d’interrogation a une faible précédence, il s’exécute donc après la comparaison >.

Cet exemple fera la même chose que le précédent :

```js
// l'opérateur de comparaison "age > 18" s'exécute en premier quoiqu'il en soit
// (pas besoin de l'envelopper entre parenthèses)
let accessAllowed = age > 18 ? true : false;
```

Mais les parenthèses rendent le code plus lisible, il est donc recommandé de les utiliser.

### Multiple ‘?’

Une séquence d’opérateurs point d’interrogation ? permettent de renvoyer une valeur qui dépend de plusieurs conditions.

### Exemple :

```js
let age = prompt('age?', 18);

let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';

alert( message );
```

Il peut être difficile au début de comprendre ce qui se passe. Mais après un examen plus approfondi, nous constatons que ce n’est qu’une séquence de tests ordinaire.

- Le premier point d’interrogation vérifie si age < 3.

- Si vrai – retourne 'Hi, baby!', Sinon, il continue avec l’expression après les deux points “:” suivants et vérifie si age < 18.

- Si vrai – retourne 'Hello!', Sinon, il continue avec l’expression après les deux points “:” suivants et vérifie si age < 100.

- Si vrai – retourne 'Greetings!', Sinon, l’expression continue après les derniers deux-points et retourne 'What an unusual age!'.

La même logique utilisant if..else :

```js
if (age < 3) {
  message = 'Hi, baby!';
} else if (age < 18) {
  message = 'Hello!';
} else if (age < 100) {
  message = 'Greetings!';
} else {
  message = 'What an unusual age!';
}
```

## 🚫 Utilisation non recommandée du ?

🔍 Parfois, on voit le point d’interrogation ? utilisé pour exécuter du code selon une condition, comme s’il remplaçait un if.

### ❌ Exemple :

```js
let company = prompt('Quelle entreprise a créé JavaScript ?', '');

(company == 'Netscape') ?
  alert('✅ Bonne réponse !') :
  alert('❌ Mauvaise réponse.');
```

➡️ Ici, on n’affecte aucune valeur à une variable, on utilise ? juste pour choisir quel alert() exécuter.
🤔 Pourquoi ce n’est pas recommandé ?

Même si ça fonctionne, ce n’est pas très lisible :

- le code devient plus confus à lire

- on gagne peu en longueur

- on perd en clarté

Nos yeux lisent plus facilement du code bien aligné verticalement comme :

### ✅ Version recommandée avec if :

```js
let company = prompt('Quelle entreprise a créé JavaScript ?', '');

if (company == 'Netscape') {
  alert('✅ Bonne réponse !');
} else {
  alert('❌ Mauvaise réponse.');
}
```

👍 Plus clair, plus facile à comprendre !
🔧 Le if est fait pour exécuter du code, pas l'opérateur ?.

### ✅ Résumé

|👉 Cas d’usage|	✅ Recommandé ?	|💬 Pourquoi ?|
|---|---|---|
|Affecter une valeur	|✅ OUI	|Lisible et pratique|
|Exécuter du code	|❌ NON	|Moins clair qu’un if classique|


## Exemple pour mieux comprendre :

```html
<!DOCTYPE html>
<html>

<body>
  <script>
    'use strict';

    let value = prompt('What is the "official" name of JavaScript?', '');

    if (value == 'ECMAScript') {
      alert('Right!');
    } else {
      alert("You don't know? ECMAScript!");
    }
  </script>


</body>

</html>
```

Une fenetre s'ouvre avec une question si on donne la bonne réponse on a "Right!" sinon "You don't know? ECMAScript!"