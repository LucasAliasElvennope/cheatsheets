# 🔄 Fonction Déclaration vs Fonction Expression

## ✅ Déclaration de fonction (classique) :

```js
function sayHi() {
  alert("Hello");
}
```

## 🧠 La fonction a un nom (sayHi) et est disponible dans tout le code, même avant sa déclaration (grâce au hoisting).

### 💡 Expression de fonction :

```js
let sayHi = function() {
  alert("Hello");
};
```

**🧠 Pas de nom après function → c’est une fonction anonyme, stockée dans la variable sayHi.**

**📦 Elle est créée et assignée au moment de l’exécution, pas avant !**

**🧪 Résumé rapide :**

|Type	|Hoisting (appel avant création)	|Nom obligatoire|	Utilisation courante|
|---|---|---|---|
|function sayHi() {}	|✅ Oui	|✅ Oui	|Fonctions globales ou utilitaires|
|let sayHi = function(){}	|❌ Non	|❌ Non (souvent)	|Fonctions anonymes ou temporaires|

## ✅ À retenir :

- Une fonction expression est une valeur ➡️ elle peut être passée en paramètre, stockée dans une variable, ou retournée d’une autre fonction.

- Elles sont souvent utilisées avec des callbacks ou des fonctions anonymes (ex : setTimeout, addEventListener, etc.)

Tu veux un exemple d’usage concret avec setTimeout ou une fonction dans une fonction ?

---

## 🔁 Qu’est-ce qu’une fonction callback ?

Une fonction callback est une fonction passée en argument à une autre fonction, qui sera appelée plus tard, une fois qu’un certain événement se produit.

### ***🧠 En gros : tu donnes une fonction à une autre fonction, pour qu’elle l’utilise au bon moment.***

✅ Exemple simple :

```js
function ask(question, yes, no) {
  if (confirm(question)) {
    yes();  // si l’utilisateur clique “OK”
  } else {
    no();   // si l’utilisateur clique “Annuler”
  }
}

function showOk() {
  alert("You agreed.");
}

function showCancel() {
  alert("You canceled the execution.");
}

ask("Do you agree?", showOk, showCancel);
```

### 📦 Que se passe-t-il ici ?

**🧠 ask est une fonction qui :**

    - pose une question (confirm)

    - appelle yes() si la réponse est OK

    - appelle no() si la réponse est Annuler

**👇 Tu lui passes en arguments :**

    - showOk ➡️ à exécuter si l’utilisateur accepte

    - showCancel ➡️ à exécuter si l’utilisateur refuse

### ✨ Résumé :

|Terme	|Signification|
|---|---|
|Callback	|Fonction qu’on donne à une autre pour qu’elle l’utilise plus tard|
|Utilité	|Déléguer une action à exécuter au bon moment|
|Avantage	|Rendre le code plus flexible et réutilisable|

### Nous pouvons utiliser les Fonctions Expressions pour écrire la même fonction mais plus courte :

```js
function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}

ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);
``` 

**Ici, les fonctions sont déclarées directement dans l’appel ask(...). Elles n’ont pas de nom et sont donc appelées anonymes. De telles fonctions ne sont pas accessibles en dehors de ask (car elles ne sont pas affectées à des variables), mais c’est exactement ce que nous voulons ici.**

## 🛠 Problème avec la déclaration conditionnelle de fonction

Lorsque nous déclarons des fonctions de manière conditionnelle à l'intérieur de blocs (comme if), il y a un problème avec la portée de la fonction. Le hoisting (élévation) des déclarations de fonction peut créer des comportements inattendus.

### Exemple problématique avec une Fonction Déclaration :

```js
let age = prompt("Quel est votre age ?", 18);

// déclarer conditionnellement une fonction
if (age < 18) {
  function welcome() {
    alert("Hello!");
  }
} else {
  function welcome() {
    alert("Greetings!");
  }
}

// ...l'utiliser plus tard
welcome(); // Erreur : "welcome" n'est pas défini
```

### ***Problème : La fonction welcome() est hoistée (élevée) mais n'est accessible que dans le bloc où elle est définie. C'est pourquoi l'appel à welcome() en dehors des blocs conditionnels génère une erreur.***

### ✅ Solution avec Fonction Expression

L'approche correcte consiste à utiliser une Fonction Expression et à assigner la fonction à une variable qui reste accessible en dehors du bloc if :

```js
let age = prompt("Quel est votre age ?", 18);

let welcome;

if (age < 18) {
  welcome = function() {
    alert("Hello!");
  };
} else {
  welcome = function() {
    alert("Greetings!");
  };
}

welcome(); // Maintenant ça fonctionne !
```

### ***Explication : La variable welcome est définie avant le bloc if, ce qui permet à la fonction d'être assignée correctement dans les deux branches du if. La fonction est ensuite accessible à l'extérieur de la condition.***

### 🚀 Simplification avec un Opérateur Terniaire

Nous pouvons également simplifier le code en utilisant un opérateur conditionnel ternaire pour attribuer directement la fonction en fonction de la condition :

```js
let age = prompt("Quel est votre age ?", 18);

let welcome = (age < 18) ?
  function() { alert("Hello!"); } :
  function() { alert("Greetings!"); };

welcome(); // Ça fonctionne aussi !
```

### ***Avantage : C’est une version plus compacte et claire du code qui permet de déclarer la fonction en fonction de la condition en une seule ligne.***

### ⚡ Résumé des Solutions :

- Problème avec la déclaration conditionnelle de fonction : Les fonctions déclarées dans un bloc if ne sont pas accessibles en dehors de ce bloc.

- Solution avec une fonction expression : Déclarez la fonction dans une variable avant d'entrer dans le if, puis assignez la fonction dans chaque branche du if.

- Simplification avec un opérateur ternaire : Utilisez l'opérateur conditionnel pour assigner directement la fonction selon la condition.