# 🧩 Fonctions

## 🔄 Pourquoi utiliser des fonctions ?

Très souvent, on doit répéter une action à plusieurs endroits dans notre script.

### 📌 Exemples :

- Afficher un message quand un visiteur se connecte

- Afficher un message quand un visiteur se déconnecte

- Et peut-être à d'autres moments aussi...

## ***👉 Au lieu de répéter le même code plusieurs fois, on crée une fonction !***

## 🛠️ C’est quoi une fonction ?

Une fonction est un bloc de code qui effectue une tâche précise.
On peut l’appeler (utiliser) autant de fois qu’on veut, sans recopier le code !

🧠 Les fonctions sont l’un des éléments clés d’un programme : elles le rendent modulaire, réutilisable et plus facile à lire.

### 🔔 On connaît déjà des fonctions toutes faites :

- alert(message) ➜ Affiche une alerte

- prompt(message, default) ➜ Demande une saisie à l’utilisateur

- confirm(question) ➜ Pose une question avec "OK" ou "Annuler"

**✅ Ces fonctions sont intégrées dans JavaScript (on les appelle des fonctions natives ou intégrées).**

---


## 🧾 Déclaration de `fonction`

### ✨ Comment créer une fonction ?

On utilise le mot-clé function, suivi :

- Du nom de la fonction 🏷️

- De parenthèses () (avec ou sans paramètres)

- Et de { accolades } pour délimiter le corps de la fonction (le code à exécuter)

## 🧱 Structure :

```js
function nomDeLaFonction(param1, param2, ..., paramN) {
  // 💬 Code à exécuter (corps de la fonction)
}
```

### 👀 Exemple simple :

```js
function showMessage() {
  alert('Hello everyone!');
}
```

➡️ Ici, showMessage est le nom de la fonction. Elle ne prend aucun paramètre et affiche une alerte.

### ***🧑‍💻 Comment l'utiliser ?***

Il suffit d’appeler la fonction par son nom, suivi de () :

```js
showMessage();
showMessage();
```

👉 Ce code va afficher deux fois une alerte avec "Hello everyone!", car on appelle la fonction deux fois ✅

### 🎯 À quoi ça sert ?

💡 L’un des grands avantages des fonctions est d’éviter la répétition de code (DRY = Don't Repeat Yourself).

**✔️ Si on veut changer le message plus tard, il suffit de le modifier à un seul endroit : dans la fonction.**

---

## 📦 Variables locales

### 📍 Définition :

Une variable locale est une variable déclarée à l’intérieur d’une fonction avec let, const ou var.

🛡️ Elle est invisible et inaccessible en dehors de cette fonction.

### 🔒 Exemple :

```js
function showMessage() {
  let message = "Hello, I'm JavaScript!"; // 🎯 Variable locale
  alert(message); // ✅ Affiche : Hello, I'm JavaScript!
}

showMessage();

alert(message); // ❌ Erreur ! "message" n'existe pas ici car local a la fonction
```

### ***🔎 Pourquoi ?***

Quand une variable est déclarée dans une fonction, elle est stockée dans une mémoire temporaire qui disparaît dès que la fonction a fini de s'exécuter.
On dit qu'elle a une portée locale (scope local).

### 🧠 Résumé :

|📌 Où ?|👀 Visible ?|
|---|---|
|À l'intérieur de la fonction|✅ Oui|
|À l’extérieur de la fonction|❌ Non (Erreur !)|

---

## 🌍 Variables externes

🔓 Une fonction peut accéder à des variables déclarées à l’extérieur d’elle-même !

### 🔎 Exemple simple :

```js
let userName = 'John';

function showMessage() {
  let message = 'Hello, ' + userName;
  alert(message);
}

showMessage(); // ✅ Affiche : Hello, John
```

➡️ La fonction utilise la variable userName déclarée à l’extérieur, car elle n’est pas redéclarée à l’intérieur.

---

## 🕶️ Masquage de variable (variable shadowing)

**🔁 Si une variable locale a le même nom qu'une variable externe, la locale l’emporte !**

***👉 La variable interne “éclipse” ou “cache” la variable externe.***

### 👀 Exemple :

```js
let userName = 'John';

function showMessage() {
  let userName = "Bob"; // 🛑 Variable locale avec le même nom

  let message = 'Hello, ' + userName;
  alert(message); // ✅ Affiche : Hello, Bob
}

showMessage();

alert(userName); // ✅ Affiche : John (la variable globale reste inchangée)
```
### 🔍 Explication :

- 📦 let userName = "Bob" est locale à la fonction.

- Elle masque la variable externe userName = 'John' pendant l’exécution de la fonction.

- En dehors de la fonction, c’est toujours la variable globale qui est utilisée.


### 🧠 Résumé :

|📌 Situation|🧠 Ce qui se passe|
|----|----|
|Même nom en interne et en externe|⚠️ La variable locale est prioritaire|
|La variable externe est ignorée|🚫 Pas utilisée dans la fonction|
|La variable globale n'est pas modifiée|✅ Reste intacte|

---

## 🌐 Variables globales

### ***📍 Définition :***

Une variable globale est une variable déclarée en dehors de toute fonction.
Elle est visible partout dans le code, même à l’intérieur des fonctions (sauf si une variable locale la masque).


### ✅ Bonnes pratiques :

**🔒 Évite d’utiliser trop de variables globales !**

**✔️ Elles peuvent être modifiées depuis n’importe où, ce qui rend le code plus difficile à maintenir et à déboguer.**

### 💡 Dans le code moderne :

- On utilise surtout des variables locales

- Les globales ne servent qu’à stocker des infos partagées dans tout le programme (ex. : configuration, état utilisateur…)

---

## 📦 Arguments

### 📌 Définition :

Nous pouvons transmettre des données arbitraires à des fonctions à l’aide de paramètres.

Dans l’exemple ci-dessous, la fonction a deux paramètres: from et text.

```js
function showMessage(from, text) { // arguments : from, text
  alert(from + ': ' + text);
}

showMessage('Ann', 'Hello!'); // Ann: Hello! (*)
showMessage('Ann', "What's up?"); // Ann: What's up? (**)
```

➡️ Ces valeurs sont copiées dans les variables locales from et text, puis utilisées dans la fonction.

- '`Ann`' est transmis à `from`
- '`Hello`!' ou "`What's up`?" est transmis à `text`

### 🧠 Résumé :

|🧩 Terme|📌 Rôle|🧠 Exemple|
|---|---|---|
|Paramètre|Variable locale dans la fonction|from, text|
|Argument|Valeur transmise lors de l’appel|'Ann', 'Hello!'|

Lorsque la fonction est appelée dans les lignes (*) et (**), les valeurs données sont copiées dans les variables locales from et text. Ensuite, la fonction les utilise.

---

## 🧙‍♂️ Valeurs par défaut des paramètres

### ***🧨 Problème :***

Quand une fonction est appelée sans certains arguments, les paramètres non fournis deviennent undefined.

### 👀 Exemple :

```js
function showMessage(from, text) {
  alert(from + ': ' + text);
}

showMessage("Ann"); // Affiche : Ann: undefined ❗
```

### 🧠 Ici :

```js
from = "Ann"
text = undefined car pas transmis
```
---

## 🧑‍💻 Valeurs par défaut des paramètres

### ***📍 Définition :***

On peut spécifier une valeur par défaut pour un paramètre, qui sera utilisée si l'argument est omis lors de l’appel de la fonction.
Cela permet d'éviter que le paramètre devienne undefined si aucun argument n'est fourni.

### ***👀 Exemple avec valeur par défaut :***

```js
function showMessage(from, text = "no text given") {
  alert(from + ": " + text);
}

showMessage("Ann"); // Affiche : Ann: no text given
```

- 🔹 Si `text` n'est pas passé, il prend la valeur `"no text given"` par défaut.
- 🔹 Sinon, la valeur transmise à `text` sera utilisée.

La valeur par défaut saute également si le paramètre existe, mais est strictement égal à `undefined`, comme ceci :

```js
showMessage("Ann", undefined); // Ann: no text given
```

Ici,  `"no text given"` est une chaîne de caractères, mais il peut s’agir d’une expression plus complexe, qui n’est évaluée et affectée que si le paramètre est manquant. Donc, cela est également possible :

```js
function showMessage(from, text = anotherFunction()) {
  // anotherFunction() est exécuté uniquement si aucun texte n'est fourni
  // son résultat devient la valeur de text
}
```

### 🔧 Résumé :

|📌 Situation|📋 Résultat|
|---|---|
|Argument ommis|Prend la valeur par défaut|
|Argument explicitement égal à undefined|Prend la valeur par défaut|
|Argument fourni|Prend la valeur fournie|
|Expression complexe (ex. fonction)|S'évalue uniquement si nécessaire|

--- 

### ⚙️ Paramètres par défaut alternatifs

📍 Vérification manuelle des paramètres

Parfois, on peut vérifier et définir une valeur par défaut au moment de l'exécution de la fonction, plutôt qu'à la déclaration de la fonction.

### 👀 Exemple avec comparaison à undefined :

```js
function showMessage(text) {
  if (text === undefined) {  // Vérifie si le paramètre est manquant
    text = 'empty message';
  }

  alert(text); // Affiche : empty message si `text` est omis
}

showMessage(); // empty message
```

🔹 Si text n'est pas passé, il devient "empty message".
🔹 Si text est fourni, il prend la valeur fournie.

### 🔧 Utilisation de l'opérateur || :

On peut aussi utiliser l'opérateur || pour attribuer une valeur par défaut si un paramètre est falsy (comme undefined, null, 0, false, etc.).

```js
function showMessage(text) {
  text = text || 'empty';  // Si `text` est falsy (undefined, null, 0...), on attribue 'empty'
  alert(text);
}

showMessage(); // empty
```

***🧠 Attention : 0, false, NaN et "" (chaîne vide) sont des valeurs falsy, donc seront aussi remplacées par la valeur par défaut ici ('empty').***

### 🚀 Utilisation de l'opérateur de coalescence des nuls ?? (meilleure solution) :

L’opérateur de coalescence des nuls ?? est une meilleure option quand on souhaite vérifier uniquement null ou undefined et ne pas affecter les autres valeurs fausses comme 0 ou false.

```js
function showCount(count) {
  alert(count ?? "unknown");  // Si count est `null` ou `undefined`, il affiche "unknown"
}

showCount(0);        // Affiche : 0
showCount(null);     // Affiche : unknown
showCount();        // Affiche : unknown
```

🔹 Ici, 0 est considéré comme une valeur valide, donc count = 0 s'affichera correctement.
🔹 Si count est null ou undefined, alors "unknown" sera affiché.

---


## 🔁 Renvoyer une valeur depuis une fonction

### 📍 Définition :

Une fonction peut renvoyer une valeur au code appelant en utilisant la directive return. Cette valeur devient le résultat de l’appel de la fonction.

### 👀 Exemple simple avec return :

```js
function sum(a, b) {
  return a + b;  // La fonction renvoie la somme de a et b
}

let result = sum(1, 2);  // La fonction sum est appelée avec 1 et 2
alert(result);  // Affiche : 3
```

🔹 Lorsque la fonction est appelée, les paramètres a et b sont additionnés et la valeur du résultat est renvoyée via return.
🔹 result reçoit cette valeur et l'affiche via alert().

### 🚀 Explication du comportement du return :

- Quand return est exécuté, l'exécution de la fonction s'arrête immédiatement.

- La valeur après return devient le résultat de la fonction.

- Si aucune valeur n'est fournie après return, la fonction renverra undefined.


## 🔁 Plusieurs occurrences de return dans une fonction

### 📍 Définition :

Il est possible d’avoir plusieurs return dans une fonction. Cela permet de renvoyer des valeurs à différents points de la fonction, selon des conditions spécifiques.

### 👀 Exemple avec plusieurs return :

```js
function checkAge(age) {
  if (age >= 18) {
    return true;  // Si l'âge est supérieur ou égal à 18, retourne true
  } else {
    return confirm('Do you have permission from your parents?');  // Sinon, demande la permission des parents
  }
}

let age = prompt('How old are you?', 18);

if (checkAge(age)) {
  alert('Access granted');  // Affiche si l'âge est valide ou si la permission est donnée
} else {
  alert('Access denied');  // Affiche si l'âge est inférieur à 18 et pas de permission
}
```

### 🔹 La fonction checkAge utilise deux return :

🔹 Si l'âge est supérieur ou égal à 18, elle retourne true.

🔹 Sinon, elle demande si l'utilisateur a la permission de ses parents via confirm() et renvoie le résultat de cette confirmation (true ou false).

**🔹 Dans le code appelant, si checkAge(age) renvoie true, l'accès est accordé, sinon il est refusé.**

--- 

## 🚫 Return sans valeur pour arrêter l'exécution

### 📍 Définition :

Lorsqu'un return est utilisé sans valeur dans une fonction, il arrête immédiatement l'exécution de la fonction et renvoie undefined.

Cela est utile lorsque tu veux mettre fin à l'exécution de la fonction avant qu'elle ne fasse quelque chose d'autre, en fonction de certaines conditions.

### 👀 Exemple avec return sans valeur :

```js
function showMovie(age) {
  if (!checkAge(age)) {  // Si checkAge retourne false
    return;  // Arrête l'exécution de showMovie et renvoie undefined
  }

  alert("Showing you the movie");  // (*) Cette alerte ne s'affichera pas si checkAge(age) retourne false
  // ...
}
```

### 🔹 Explication :

🔹 Si checkAge(age) retourne false, la fonction showMovie s'arrête immédiatement grâce à return.

🔹 L'alerte "Showing you the movie" ne sera jamais affichée car l'exécution de la fonction a été arrêtée avant grâce au return.

### 🚀 Résumé de l'utilisation de return sans valeur :

🔹 return; dans une fonction arrête son exécution et renvoie undefined.

🔹 Cela permet de prévenir l'exécution d'autres actions (comme des alertes, des calculs, etc.), en fonction de conditions spécifiques.

---

## 🌀 Return vide et undefined

### 📍 Définition :

Une fonction avec un return vide ou sans valeur renvoie undefined par défaut. Cela signifie que si la fonction ne renvoie rien, JavaScript renvoie automatiquement la valeur undefined.

### 👀 Exemple de fonction avec return vide :

```js
function doNothing() { /* vide */ }

alert( doNothing() === undefined ); // true
```

### 🔹 Explication :

🔹 La fonction doNothing ne renvoie rien.

🔹 Par défaut, cela revient à renvoyer undefined.

### 🚀 Exemple de return sans valeur (identique à return undefined) :

```js
function doNothing() {
  return;  // return vide, équivalent à return undefined
}

alert( doNothing() === undefined ); // true
```

### 🔹 Explication :

🔹 return; sans valeur explicite dans la fonction est identique à return undefined.

🔹 Cela signifie que si la fonction n'a pas de valeur après return, elle renverra undefined.

### 🧠 Résumé :

🔹 return vide renvoie undefined par défaut.

🔹 return; et return undefined sont identiques.

---

## 📝 Nommer une fonction

### 🤔 Pourquoi c’est important ?

Le nom d’une fonction doit être clair, précis et décrire l’action qu’elle effectue.

**💡 L’objectif : comprendre le rôle de la fonction rien qu’en lisant son nom !**

### ✅ Bonnes pratiques :

- 🟢 Utiliser un verbe → Une fonction fait une action, donc commence par un verbe clair.

- 🟢 Sois précis → Le nom doit résumer le rôle exact de la fonction.

- 🟢 Adopter un préfixe cohérent → Cela facilite la lecture du code et le travail en équipe.

### 🔤 Préfixes recommandés et leurs rôles :

| 🔤 Préfixe	|📌 Action attendue|
|---|---|
|show...	|Affiche quelque chose à l’utilisateur 🖥️|
|get...	|Récupère une valeur et la renvoie 📥|
|calc...	|Calcule une valeur et la renvoie ➗|
|create...	|Crée un objet ou un élément 🧱|
|check...	|Vérifie une condition, renvoie true/false ✅❌|

### 📚 Exemples concrets :

```js
showMessage()        // Affiche un message
getAge()             // Récupère l’âge
calcSum(a, b)        // Calcule la somme de deux nombres
createForm()         // Crée un formulaire (et le retourne)
checkPermission()    // Vérifie une autorisation (true/false)
```

### 🎯 Résumé :

🔹 ✔️ Utilise des verbes clairs

🔹 ✔️ Sois cohérent dans le nommage

🔹 ✔️ Utilise des préfixes logiques pour décrire le comportement de la fonction

--- 

## 🧩 Fonctions == Commentaires vivants

🛠️ Une fonction bien écrite sert à décomposer le code, le rendre plus lisible, testable et débogable.

### 🎯 Règle d’or :

🔹 Une fonction = une seule tâche précise

🔹 Si la tâche est trop grosse ➜ découpe-la en fonctions plus petites.

💬 Chaque fonction bien nommée agit comme un commentaire auto-explicite.

📊 Exemple : showPrimes(n)

### ❌ Version complexe avec un label :

```js
function showPrimes(n) {
  nextPrime: for (let i = 2; i < n; i++) {
    for (let j = 2; j < i; j++) {
      if (i % j == 0) continue nextPrime;
    }
    alert(i); // nombre premier
  }
}
```

🧠 Difficile à lire à cause du label et des boucles imbriquées.

✅ Version claire avec une fonction :

```js
function showPrimes(n) {
  for (let i = 2; i < n; i++) {
    if (!isPrime(i)) continue;
    alert(i); // nombre premier
  }
}

function isPrime(n) {
  for (let i = 2; i < n; i++) {
    if (n % i == 0) return false;
  }
  return true;
}
```

🟢 Beaucoup plus lisible grâce à isPrime(n) qui explique ce qu’elle fait par son nom !
📌 On comprend directement : "Si ce n’est pas un nombre premier, on saute."

### 🧠 À retenir :

✅ Créer une fonction même si elle est utilisée une seule fois, ça :

- rend le code plus propre 🧼

- facilite la relecture 👀

- documente l’intention du code 📖

---

## Conclusion

### 🛠️ Déclaration d'une fonction

```js
function nom(param1, param2, ...) {
  // code
}
```

### 🧾 Ce qu’il faut retenir :

✅ Les paramètres sont copiés dans des variables locales à la fonction.

🚫 Les variables locales ne sont pas accessibles à l’extérieur de la fonction.

🔁 Une fonction peut renvoyer une valeur avec return.

→ Sinon, elle renvoie undefined.

### 🌱 Bonnes pratiques

**📌 Préfère :**

- ➕ Utiliser des paramètres et travailler localement

- 🚫 Éviter les effets de bord (modifier des variables externes)

🎯 Une fonction claire ➜ entrée (paramètres) → traitement → sortie (return)

🎯 Une fonction bien faite = facile à lire, tester et réutiliser 🔁

🏷️ Nommage des fonctions

🗣️ Une fonction est une action, donc son nom est généralement un verbe.

📚 Préfixes recommandés :

|Préfixe	|Signification|
|---|---|
|get...	|🔄 Récupère une valeur|
|show...	|👁️ Affiche quelque chose|
|calc...	|➕ Calcule une valeur|
|create...	|🧱 Crée un objet ou un élément|
|check...	|✅ Vérifie une condition (true/false)|

### ***🧠 Un bon nom ➜ décrit l’intention et évite les commentaires inutiles***
