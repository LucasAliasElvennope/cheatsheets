# Comprendre et reproduire le code de comptage et de somme 🔢➕➖

Ce document explique pas à pas le code JavaScript pour compter les nombres positifs et sommer les nombres négatifs dans un tableau.

## 1. Objectif 🎯

Le but de cette fonction est de prendre un tableau d'entiers en entrée et de retourner un nouveau tableau contenant deux éléments :

* Le **nombre total** d'entiers positifs dans le tableau d'entrée.
* La **somme** de tous les entiers négatifs dans le tableau d'entrée.

**Important :** Le nombre zéro (0) n'est considéré ni comme positif ni comme négatif et sera ignoré.

## 2. Structure de la fonction ⚙️

La fonction est nommée `countPositivesSumNegatives` et prend un seul argument : `input`, qui représente le tableau d'entiers.

```javascript
function countPositivesSumNegatives(input) {
  // ... le code sera ici ...
}
```


## 3. Gestion des cas spéciaux ⚠️

Avant de commencer à traiter le tableau, il est important de vérifier si l'entrée est invalide. Selon l'énoncé, si le tableau d'entrée est null (n'existe pas) ou s'il est vide ([]), nous devons retourner un tableau vide.

```javascript
  if (input === null || input.length === 0) {
    return [];
  }

    input === null: Vérifie si la variable input ne contient aucune valeur.
    input.length === 0: Vérifie si le tableau input ne contient aucun élément.
    || (l'opérateur "ou") : La condition est vraie si l'une OU l'autre de ces vérifications est vraie.
    return [];: Si la condition est vraie, on retourne immédiatement un tableau vide.
```

## 4. Initialisation des compteurs et de la somme ⏱️

Avant de parcourir le tableau, nous devons initialiser deux variables pour stocker nos résultats :

```javascript
  let positif = 0;
  let négatif = 0;

    positif: Une variable initialisée à 0. Elle sera utilisée pour compter le nombre d'entiers positifs rencontrés. Nous utilisons let car la valeur de cette variable va changer.
    négatif: Une variable initialisée à 0. Elle sera utilisée pour stocker la somme des entiers négatifs rencontrés. Nous utilisons également let car sa valeur va être mise à jour.
```

## 5. Parcours du tableau 🚶‍♀️

Pour examiner chaque élément du tableau d'entrée, nous utilisons une boucle for:

```javascript
  for (let i = 0; i < input.length; i++) {
    // ... traitement de chaque élément ...
  }

    let i = 0: Initialise un compteur i à 0. i représente l'index de l'élément actuel dans le tableau.
    i < input.length: La boucle continue tant que i est inférieur à la taille totale du tableau.
    i++: Incrémente i de 1 après chaque itération pour passer à l'élément suivant.
```

## 6. Vérification de chaque élément 🧐

À l'intérieur de la boucle, pour chaque élément input[i], nous effectuons des vérifications pour déterminer s'il est positif, négatif ou zéro:

```javascript

    if (input[i] > 0) {
      positif++;
    } else if (input[i] < 0) {
      négatif += input[i];
    }
    // Si input[i] est égal à zéro, on ne fait rien.

    if (input[i] > 0): Si l'élément actuel est supérieur à 0, c'est un nombre positif. Dans ce cas, nous incrémentons le compteur positif de 1 (positif++).
    else if (input[i] < 0): Si l'élément actuel n'est pas positif, nous vérifions s'il est inférieur à 0. Si c'est le cas, c'est un nombre négatif. Nous ajoutons sa valeur à la variable négatif (négatif += input[i], qui est équivalent à négatif = négatif + input[i]).
    Le cas du zéro : Si input[i] n'est ni supérieur à 0 ni inférieur à 0, cela signifie qu'il est égal à zéro. Selon les instructions, nous ne faisons rien dans ce cas.
```

## 7. Retour du résultat final 🎉

Une fois que la boucle for a terminé de parcourir tous les éléments du tableau, nous avons le compte final des nombres positifs dans la variable positif et la somme finale des nombres négatifs dans la variable négatif. Nous devons retourner un nouveau tableau contenant ces deux valeurs dans l'ordre spécifié : [nombre de positifs, somme des négatifs].

```javascript
  return [positif, négatif];
}
```

## 8. Exemple d'utilisation 🧪

Pour mieux comprendre, voici un exemple d'utilisation de la fonction :

```javascript
const monTableau = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15];
const resultat = countPositivesSumNegatives(monTableau);
console.log(resultat); // Output: [10, -65]
```

Dans cet exemple, il y a 10 nombres positifs et la somme des nombres négatifs est -11 + (-12) + (-13) + (-14) + (-15) = -65.