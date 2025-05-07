# 🧱 Les Objets en JavaScript

## 📌 C’est quoi un objet ?

Un objet est une structure spéciale qui permet de stocker plusieurs valeurs ensemble, qui fonctionne sous forme de paires clé/valeur.

***🧊 Contrairement aux types primitifs (comme les nombres, les chaînes…), les objets peuvent contenir plusieurs données variées — comme une boîte de rangement avec des étiquettes ! 📦🏷️***


**🗃️ Métaphore :**

Pense à un objet comme une armoire de bureau :

- Chaque tiroir (= clé 🔑) a une étiquette (le nom).

- À l’intérieur, il y a un fichier (= valeur 📄).

- Tu peux ajouter, modifier, ou supprimer ces fichiers facilement !

## ✍️ Créer un objet

Il existe deux façons de créer un objet vide :

```js
let monObjet = {};         // ✅ façon courte
let monObjet = new Object(); // ✅ façon plus "classique"
```

## 📚 En résumé :

- ✅ Clé = nom de la propriété (toujours une chaîne 🧾)

- ✅ Valeur = n’importe quel type de donnée : nombre, chaîne, booléen, fonction, tableau, objet…

---

## 🧾 Objets : littéraux et propriétés

### 🧱 Créer un objet avec des propriétés

Tu peux définir directement des propriétés dans un objet avec des accolades {} :

```js
let user = {
  name: "John",  // clé : "name", valeur : "John"
  age: 30        // clé : "age", valeur : 30
};
```

***👆 C’est ce qu’on appelle un littéral d’objet !***
