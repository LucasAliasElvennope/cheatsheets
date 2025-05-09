# Switch

L'instruction switch en JavaScript permet de simplifier la gestion de plusieurs conditions similaires, par rapport à une série de vérifications avec if...else. Elle permet de tester une valeur contre plusieurs possibilités (des cas). C’est souvent plus clair et plus facile à maintenir que d'utiliser plusieurs if.

## Syntaxe de la déclaration switch

La structure de base d’un switch ressemble à ceci :

```js
switch(x) {
  case 'value1':  // Si (x === 'value1')
    // Exécute ce code si x est égal à 'value1'
    break;  // Arrête l'exécution du switch ici

  case 'value2':  // Si (x === 'value2')
    // Exécute ce code si x est égal à 'value2'
    break;

  default:  // Si aucune des conditions ci-dessus n'est vraie
    // Exécute ce code si aucune correspondance n'a été trouvée
    break;
}
```

## Explication détaillée


`switch(x)` :
On commence par tester la valeur de x.

`case 'value1'` :
Si x est strictement égal (===) à 'value1', le code associé à ce bloc case sera exécuté.

`break` :
Après chaque case, on utilise généralement le mot-clé break. Cela permet de sortir du switch une fois qu’un cas est trouvé et exécuté. Si break est omis, l’exécution continuera dans le case suivant, ce qui peut être utile dans certains cas, mais ce n'est pas courant pour la plupart des situations.

`default` :
C’est le cas par défaut. Si aucune des conditions dans les case ne correspond à la valeur de x, le code sous le default sera exécuté. Le default est facultatif, mais il est utile lorsque tu veux avoir un comportement prévu dans le cas où aucune valeur ne correspond.

### Exemple pratique

```js
let fruit = 'banane';

switch(fruit) {
  case 'pomme':
    console.log('C’est une pomme!');
    break;
  case 'banane':
    console.log('C’est une banane!');
    break;
  case 'orange':
    console.log('C’est une orange!');
    break;
  default:
    console.log('Fruit inconnu');
}
```

## Ce qui se passe :

`switch(fruit)` vérifie la valeur de fruit, qui est 'banane'.

Il compare cette valeur avec les valeurs des case : 'pomme', 'banane', 'orange'.

Quand il trouve une correspondance avec 'banane', il exécute le code associé à ce case, donc console.log('C’est une banane!').

`break` fait sortir du switch, empêchant l'exécution des autres case.

Si fruit avait été une valeur différente (par exemple, 'kiwi'), le bloc default aurait été exécuté.

### Pourquoi utiliser switch ?

Lisibilité améliorée : Quand tu as plusieurs vérifications de conditions qui comparent une même variable à plusieurs valeurs, le switch est plus propre que plusieurs if...else.

Maintenance facilitée : Si tu veux ajouter un autre cas, tu n’as qu’à ajouter une nouvelle ligne case, ce qui rend le code plus modulaire.

## Exemple sans switch (en utilisant if...else)

```js
let fruit = 'banane';

if (fruit === 'pomme') {
  console.log('C’est une pomme!');
} else if (fruit === 'banane') {
  console.log('C’est une banane!');
} else if (fruit === 'orange') {
  console.log('C’est une orange!');
} else {
  console.log('Fruit inconnu');
}
```

Dans ce cas, avec if...else, le code devient plus lourd et moins facile à lire quand il y a beaucoup de conditions à vérifier. Le switch permet de simplifier et rendre le code plus clair.

### ***Conclusion***

Le switch est une alternative plus propre et plus lisible à une série de if...else quand il s'agit de vérifier une même variable contre plusieurs valeurs possibles.

L'utilisation de break permet d'éviter l'exécution non intentionnelle des autres case après avoir trouvé une correspondance.

Le default permet de gérer les cas où aucune des valeurs comparées ne correspond.

### ***UN EXEMPLE***

Un exemple de switch (le code exécuté est mis en évidence) :

```js
let a = 2 + 2;

switch (a) {
  case 3:
    alert( 'Too small' );
    break;
  case 4:
    alert( 'Exactly!' );
    break;
  case 5:
    alert( 'Too big' );
    break;
  default:
    alert( "I don't know such values" );
}
```

Ici, le switch commence à comparer a avec le premier case dont la valeur est 3. La correspondance échoue.

Ensuite 4, c’est une correspondance. L’exécution commence donc à partir du case 4 jusqu’au prochain break.

S’il n’y a pas de break, l’exécution continue avec le case suivant sans aucun contrôle.

## 🔁 1. Exemple sans break :

```js
let a = 2 + 2;

switch (a) {
  case 3:
    alert('Too small');
  case 4:
    alert('Exactly!');
  case 5:
    alert('Too big');
  default:
    alert("I don't know such values");
}
```

### ✅ Analyse :

- a = 4, donc le switch compare chaque case à 4.

- Il trouve case 4, donc il commence l'exécution à partir de là.

Mais comme il n'y a pas de break, il continue les blocs suivants même s'ils ne correspondent pas !

### 🧨 Résultat :

1. alert("Exactly!")
2. alert("Too big")
3. alert("I don't know such values")

**💡 Ce comportement est appelé "fall-through" :**

Une fois qu’un case est déclenché, tout ce qui suit est exécuté jusqu'à un break ou la fin du switch.

### 🧠 2. Case avec expression :

```js
let a = "1";
let b = 0;

switch (+a) { // +a convertit "1" en nombre => 1
  case b + 1: // 0 + 1 => 1
    alert("this runs, because +a is 1, exactly equals b+1");
    break;

  default:
    alert("this doesn't run");
}
```

### 🧨 Résultat :

- +a → "1" devient 1 (grâce à l’opérateur unaire +)

- b + 1 → 0 + 1 → 1

- Donc le case correspond → ✅ l’alerte "this runs..." s’affiche.

- break empêche l’exécution du default.

### 📝 À retenir :

- ***⚠ Sans break, tous les case suivants seront exécutés.***

- Switch utilise une comparaison stricte (===), donc les types doivent aussi correspondre.

## 🔁 Groupement de case

Quand plusieurs case doivent mener à la même action, tu peux les empiler les uns à la suite des autres, sans break intermédiaire, jusqu’à ce que le bloc de code partagé commence.

### ***📌 Exemple expliqué pas à pas :***

```js
{{ ... }}

switch (a) {
  case 4:
    alert('Right!');
    break;

  case 3: // 👇 Ces deux cases sont regroupées
  case 5:
    alert('Wrong!');
    alert("Why don't you take a math class?");
    break;

  default:
    alert('The result is strange. Really.');
}
```

### ***🧠 Explication :***

- a = 4, donc switch(4) :

  - Il vérifie case 4 ✅ => exécute alert('Right!'), puis break : fin du switch.

- Si a = 3 ou a = 5 :

  - Il n’y a pas de code dans case 3, donc il continue à case 5 et exécute les deux alertes.

  - Ensuite break, donc fin.

- Si a n’est ni 3, 4, ni 5, le bloc default est exécuté.

### ***🧩 Pourquoi ça marche ?***

Parce que switch lit ligne par ligne à partir du case qui correspond, et s'arrête uniquement lorsqu’il trouve un break ou la fin du switch.

### ✅ Avantage

Cela rend ton code :

- ✨ Plus lisible

- 🔁 Moins répétitif

- 💡 Plus expressif