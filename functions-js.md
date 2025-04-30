# 📝 Cheat-Sheet : Les Fonctions en JavaScript

## 📦 Déclaration d'une fonction

### 1. Fonction simple
```js
function maFonction() {
  console.log("Hello !");
}
```

### 2. Fonction avec paramètres

```js
function saluer(prenom) {
  console.log("Bonjour " + prenom + "!");
}
```

### 🧮 Appeler une fonction

```js
maFonction();  // Appel de la fonction
saluer("Alice");  // Affiche "Bonjour Alice!"
```

### 🧩 Retourner une valeur

```js
function addition(a, b) {
  return a + b;
}


let resultat = addition(3, 5);  // retourne 8
console.log(resultat);  // Affiche 8
```

### 🛠️ Fonction sans valeur de retour

```js
function afficherMessage() {
  console.log("Message affiché !");
}

afficherMessage();  // Affiche "Message affiché !"
```

###🧭 Exemple avec un bouton

```html
<button onclick="changerMessage()">Cliquez-moi!</button>
<p id="message"></p>

<script>
  function changerMessage() {
    document.getElementById("message").textContent = "Vous avez cliqué sur le bouton!";
  }
</script>
```

### 📚 Résumé rapide :

- Déclaration : function maFonction() { ... }

- Appel : maFonction();

- Retour : return valeur;

- Paramètre : function saluer(nom) { ... }

- Sans retour : console.log();
