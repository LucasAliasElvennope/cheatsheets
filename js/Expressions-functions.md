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