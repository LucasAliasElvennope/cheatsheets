# ⚙️ Cheat Sheet : Classes en JavaScript

## 🧱 Définition d'une classe

```javascript
class MaClasse {
  // 🏗️ Constructeur : Initialise les objets
  constructor(nom, age) {
    this.nom = nom;       // 🏷️ Propriété
    this.age = age;       // 🔢 Autre propriété
  }

  // 🗣️ Méthode : Fonction de l'objet
  saluer() {
    console.log(`👋 Bonjour, je m'appelle ${this.nom} et j'ai ${this.age} ans.`);
  }

  // 🎂 Autre méthode
  anniversaire() {
    this.age++;
    console.log(`🥳 Joyeux anniversaire ! J'ai maintenant ${this.age} ans.`);
  }

  // 🤫 Méthode statique : Appartient à la classe
  static messageSpecial() {
    console.log("✨ Ceci est un message spécial de la classe MaClasse.");
  }
}
```

## 🛠️ Création d'objets (instances)

```javascript
const personne1 = new MaClasse("Alice", 30);
const personne2 = new MaClasse("Bob", 25);

// Access ➡️ aux propriétés
console.log(personne1.nom); // Output: Alice
console.log(personne2.age); // Output: 25

// Appel 📞 des méthodes
personne1.saluer();
personne2.anniversaire();

// Utilisation ⚙️ d'une méthode statique
MaClasse.messageSpecial();
```

## 🧬 Héritage (extends)

```javascript
class Etudiant extends MaClasse {
  constructor(nom, age, ecole) {
    super(nom, age);     // 🔑 Appelle le constructeur parent
    this.ecole = ecole;   // 🏫 Nouvelle propriété
  }

  // 📚 Nouvelle méthode
  etudier() {
    console.log(`📖 ${this.nom} étudie à ${this.ecole}.`);
  }

  // 🗣️ Redéfinition de méthode (polymorphisme)
  saluer() {
    console.log(`🎓 Bonjour, je suis ${this.nom}, étudiant à ${this.ecole}.`);
  }
}

const etudiant1 = new Etudiant("Charlie", 20, "Université XYZ");
etudiant1.saluer();
etudiant1.etudier();
console.log(etudiant1.age); // Hérité de MaClasse

```
