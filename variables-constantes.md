# 📝 Cheat-Sheet : Variables et Constantes en JavaScript

## 💡 Déclaration d'une variable

- `let` : Crée une variable modifiable

```js
let age = 25;
age = 26; // La valeur peut être modifiée
```

- `const` : Crée une constante (sa valeur ne peut pas être changée)

```js
const nom = "Alice";
// nom = "Bob"; // Erreur ! Une constante ne peut pas être modifiée
```

## 🔧 Règles de nommage des variables

- Commence par une lettre, un chiffre, $, ou _

- Pas d'espaces ni de caractères spéciaux (sauf $ et _)

- Utilise camelCase pour les noms composés : monNomDeVariable

**Exemples valides** :

```js
let nomUtilisateur;
let scoreTotal;
const PI = 3.14;
```

**Exemples invalides** :

```js
let 2score; // Ne peut pas commencer par un chiffre
let nom-utilisateur; // Le tiret n'est pas autorisé
```

## 🧭 Différences entre let et const

| Propriété	| let	| const	|
| Modifiable ?	| Oui	| Non	|
| Valeur initiale ?	| Pas nécessaire	| Obligatoire (doit être initialisée lors de la déclaration)	|
| Exemple	| let age = 25;	| const PI = 3.14;

## 🛠️ Exemples pratiques

**Créer et utiliser une variable** :

```js
let nombre = 10;
nombre = nombre + 5; // nombre devient 15
console.log(nombre); // Affiche 15
```

**Créer et utiliser une constante** :

```js
const couleur = "bleu";
// couleur = "rouge"; // Erreur ! Une constante ne peut pas être modifiée
console.log(couleur); // Affiche "bleu"
```

## 📏 Bonne pratique de nommage

- Choisis des noms clairs et significatifs.

- Utilise des noms de variables qui décrivent bien leur contenu (ex : age, nomUtilisateur).

## ⚠️ Attention aux erreurs fréquentes

**Modification d'une constante** :

```js
const utilisateur = "Alice";
utilisateur = "Bob"; // ❌ Erreur : modification d'une constante
```

**Déclaration incorrecte d'une constante** :

```js
const prix; // ❌ Erreur : une constante doit être initialisée
```

