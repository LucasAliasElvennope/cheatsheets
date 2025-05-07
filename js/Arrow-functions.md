# 🔍 C’est quoi une fonction fléchée ?

Une fonction fléchée (ou arrow function) est une façon raccourcie d’écrire une fonction en JavaScript 💡

Elle a été introduite dans ES6 pour rendre le code plus rapide à écrire et souvent plus lisible, surtout pour les fonctions simples.

## 🆚 Différence avec une fonction classique :

|Fonction classique	|Fonction fléchée|
|---|---|
|function()	|() =>|
|Peut avoir plusieurs lignes	|Idéale pour une seule ligne|
|Utilise function	|Utilise une flèche =>|
|Gère son propre this (contexte)	|🔥 Ne change pas le this (hérite)|


### 👇 Fonction classique :

```js
function direBonjour(nom) {
  return "Bonjour " + nom;
}
```

### 🚀 Fonction fléchée équivalente :

```js
let direBonjour = (nom) => "Bonjour " + nom;
```

### 💡 C’est exactement la même chose, juste plus rapide à écrire !

---

## 🔁 Fonction fléchée multiligne

Les fonctions fléchées simples prennent des arguments à gauche de => et renvoient directement l’expression à droite.

Pour plus de complexité (plusieurs lignes), on utilise des {} et il faut alors ajouter un return explicite.

### ***👇 Comme cela :***

```js
let sum = (a, b) => {  // Les accolades ouvre une fonction multiligne
  let result = a + b;
  return result; // si nous utilisons des accolades, nous avons besoin d'un "return" explicite
};

alert( sum(1, 2) ); // 3
```

---

## 📝 Résumé

Les fonctions fléchées sont pratiques pour des actions simples, en particulier pour les one-liners. Ils se déclinent en deux variantes :

- Sans accolades : (...args) => expression – le côté droit est une expression : la fonction l’évalue et retourne le résultat. Les parenthèses peuvent être omises s’il n’y a      qu’un seul argument, par ex. n => n*2.

- Avec accolades : (...args) => { body } – les accolades nous permet des déclarations multiples au sein de la fonction, mais nous devons ajouter un return explicite pour retourner quelque chose.
