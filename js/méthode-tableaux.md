# 🛠️ Cheat-Sheet des Méthodes de Tableaux JavaScript 🚀

## 🔄 Modification du Tableau Original 🔄

* `push(élément1, ..., élémentN)`: Ajoute à la fin.
    ```javascript
    let fruits = ["pomme", "banane"];
    fruits.push("orange"); // fruits devient ["pomme", "banane", "orange"]
    console.log(fruits); // Output: ["pomme", "banane", "orange"]
    ```
* `pop()`: Supprime le dernier. 💨
    ```javascript
    let fruits = ["pomme", "banane", "orange"];
    let dernier = fruits.pop(); // dernier vaut "orange", fruits devient ["pomme", "banane"]
    console.log(fruits); // Output: ["pomme", "banane"]
    console.log(dernier); // Output: orange
    ```
* `unshift(élément1, ..., élémentN)`: Ajoute au début. 🆕
    ```javascript
    let fruits = ["banane", "orange"];
    fruits.unshift("fraise"); // fruits devient ["fraise", "banane", "orange"]
    console.log(fruits); // Output: ["fraise", "banane", "orange"]
    ```
* `shift()`: Supprime le premier. ➡️
    ```javascript
    let fruits = ["fraise", "banane", "orange"];
    let premier = fruits.shift(); // premier vaut "fraise", fruits devient ["banane", "orange"]
    console.log(fruits); // Output: ["banane", "orange"]
    console.log(premier); // Output: fraise
    ```
* `splice(index, nombreASupprimer, élément1, ..., élémentN)`: Modifie (supprime et/ou ajoute). ✂️➕
    ```javascript
    let fruits = ["pomme", "banane", "orange"];
    fruits.splice(1, 1, "kiwi"); // À l'index 1, supprime 1 élément et ajoute "kiwi"
    console.log(fruits); // Output: ["pomme", "kiwi", "orange"]

    let nombres = [1, 2, 3, 4, 5];
    nombres.splice(2, 0, 10, 20); // À l'index 2, ne supprime rien et ajoute 10 et 20
    console.log(nombres); // Output: [1, 2, 10, 20, 3, 4, 5]
    ```
* `reverse()`: Inverse l'ordre. 🔄
    ```javascript
    let nombres = [1, 2, 3];
    nombres.reverse(); // nombres devient [3, 2, 1]
    console.log(nombres); // Output: [3, 2, 1]
    ```
* `sort(fonctionDeComparaison)`: Trie. <0xC2><0xAE>
    ```javascript
    let fruits = ["orange", "banane", "pomme"];
    fruits.sort(); // Trie alphabétiquement
    console.log(fruits); // Output: ["banane", "orange", "pomme"]

    let nombres = [10, 5, 8, 1];
    nombres.sort((a, b) => a - b); // Trie numériquement (ordre croissant)
    console.log(nombres); // Output: [1, 5, 8, 10]
    ```
* `fill(valeur, indexDébut, indexFin)`: Remplit avec une valeur. 🖌️
    ```javascript
    let nombres = [1, 2, 3, 4];
    nombres.fill(0, 1, 3); // Remplit de 0 de l'index 1 (inclus) à 3 (exclus)
    console.log(nombres); // Output: [1, 0, 0, 4]

    let zeros = new Array(5).fill(0); // Crée un tableau de 5 zéros
    console.log(zeros); // Output: [0, 0, 0, 0, 0]
    ```

## 🆕 Création de Nouveaux Tableaux ou Sous-Tableaux 🆕

* `slice(indexDébut, indexFin)`: Extrait une portion (copie superficielle). 🔪
    ```javascript
    let fruits = ["pomme", "banane", "orange", "kiwi"];
    let agrumes = fruits.slice(2); // À partir de l'index 2 jusqu'à la fin
    console.log(agrumes); // Output: ["orange", "kiwi"]

    let milieu = fruits.slice(1, 3); // De l'index 1 (inclus) à 3 (exclus)
    console.log(milieu); // Output: ["banane", "orange"]
    ```
* `concat(valeur1, valeur2, ..., valeurN)`: Concatène (fusionne). 🔗
    ```javascript
    let arr1 = [1, 2];
    let arr2 = [3, 4];
    let arr3 = arr1.concat(arr2); // [1, 2, 3, 4]
    console.log(arr3); // Output: [1, 2, 3, 4]

    let lettres = ["a", "b"].concat("c", ["d", "e"]);
    console.log(lettres); // Output: ["a", "b", "c", "d", "e"]
    ```

## 🔍 Accès et Recherche d'Éléments 🔎

* `indexOf(élémentRecherché, indexDébut)`: Premier index trouvé. 📍
    ```javascript
    let animaux = ["chat", "chien", "oiseau", "chien"];
    console.log(animaux.indexOf("chien")); // Output: 1
    console.log(animaux.indexOf("chien", 2)); // Output: 3 (recherche à partir de l'index 2)
    console.log(animaux.indexOf("poisson")); // Output: -1 (pas trouvé)
    ```
* `lastIndexOf(élémentRecherché, indexDébut)`: Dernier index trouvé. 🔚
    ```javascript
    let animaux = ["chat", "chien", "oiseau", "chien"];
    console.log(animaux.lastIndexOf("chien")); // Output: 3
    console.log(animaux.lastIndexOf("chien", 2)); // Output: 1 (recherche en arrière jusqu'à l'index 2)
    ```
* `includes(élémentRecherché, indexDébut)`: Vérifie si l'élément existe. ✅/❌
    ```javascript
    let fruits = ["pomme", "banane", "orange"];
    console.log(fruits.includes("banane")); // Output: true
    console.log(fruits.includes("kiwi")); // Output: false
    console.log(fruits.includes("pomme", 1)); // Output: false (recherche à partir de l'index 1)
    ```
* `find(fonction)`: Retourne la **valeur** du premier correspondant. ✨
    ```javascript
    let nombres = [10, 5, 8, 12];
    let premierGrand = nombres.find(nombre => nombre > 10); // Retourne 12
    console.log(premierGrand); // Output: 12
    ```
* `findIndex(fonction)`: Retourne l'**index** du premier correspondant. 🔢
    ```javascript
    let nombres = [10, 5, 8, 12];
    let indexPremierGrand = nombres.findIndex(nombre => nombre > 10); // Retourne 3
    console.log(indexPremierGrand); // Output: 3
    ```
* `at(index)`: Accède à l'élément à l'index (permet les index négatifs). 🎯
    ```javascript
    let couleurs = ["rouge", "vert", "bleu"];
    console.log(couleurs.at(0)); // Output: "rouge"
    console.log(couleurs.at(2)); // Output: "bleu"
    console.log(couleurs.at(-1)); // Output: "bleu" (dernier élément)
    console.log(couleurs.at(-2)); // Output: "vert" (avant-dernier élément)
    ```

## 🚶‍♀️ Itération sur les Éléments 🚶‍♂️

* `forEach(fonction)`: Exécute une fonction pour chaque élément. ⚙️
    ```javascript
    let nombres = [1, 2, 3];
    nombres.forEach(nombre => console.log(nombre * 2)); // Output: 2, 4, 6
    ```
* `map(fonction)`: Crée un **nouveau** tableau avec les résultats. 🗺️
    ```javascript
    let nombres = [1, 2, 3];
    let doubles = nombres.map(nombre => nombre * 2); // doubles vaut [2, 4, 6]
    console.log(doubles); // Output: [2, 4, 6]
    ```
* `filter(fonction)`: Crée un **nouveau** tableau avec les éléments qui passent le test. 🧪
    ```javascript
    let nombres = [1, 2, 3, 4, 5];
    let pairs = nombres.filter(nombre => nombre % 2 === 0); // pairs vaut [2, 4]
    console.log(pairs); // Output: [2, 4]
    ```
* `reduce(fonction(accumulateur, valeurCourante, index, tableau), valeurInitiale)`: Réduit à une seule valeur (de gauche à droite). ⬇️
    ```javascript
    let nombres = [1, 2, 3, 4];
    let somme = nombres.reduce((accumulateur, valeurCourante) => accumulateur + valeurCourante, 0); // somme vaut 10
    console.log(somme); // Output: 10
    ```
* `reduceRight(fonction(accumulateur, valeurCourante, index, tableau), valeurInitiale)`: Réduit à une seule valeur (de droite à gauche). ⬅️⬇️
    ```javascript
    let nombres = [1, 2, 3];
    let résultat = nombres.reduceRight((accumulateur, valeurCourante) => accumulateur - valeurCourante, 0); // résultat vaut -6 (0 - 3 - 2 - 1)
    console.log(résultat); // Output: -6
    ```
* `every(fonction)`: Vérifie si **tous** les éléments passent le test. 👍/👎
    ```javascript
    let nombres = [10, 12, 15, 20];
    let tousGrands = nombres.every(nombre => nombre > 9); // tousGrands vaut true
    console.log(tousGrands); // Output: true

    let certainsPetits = nombres.every(nombre => nombre < 15); // certainsPetits vaut false
    console.log(certainsPetits); // Output: false
    ```
* `some(fonction)`: Vérifie si **au moins un** élément passe le test. 👍/👎
    ```javascript
    let nombres = [5, 8, 12, 3];
    let auMoinsUnGrand = nombres.some(nombre => nombre > 10); // auMoinsUnGrand vaut true
    console.log(auMoinsUnGrand); // Output: true

    let tousPetits = nombres.some(nombre => nombre < 0); // tousPetits vaut false
    console.log(tousPetits); // Output: false
    ```
* `entries()`: Retourne un itérateur clé/valeur. 🔑➡️ Value
    ```javascript
    let fruits = ["pomme", "banane"];
    for (const [index, element] of fruits.entries()) {
      console.log(`${index}: ${element}`); // Output: 0: pomme, 1: banane
    }
    ```
* `keys()`: Retourne un itérateur des indices (clés). 🗝️
    ```javascript
    let fruits = ["pomme", "banane"];
    for (const key of fruits.keys()) {
      console.log(key); // Output: 0, 1
    }
    ```
* `values()`: Retourne un itérateur des valeurs. ➡️ Value
    ```javascript
    let fruits = ["pomme", "banane"];
    for (const value of fruits.values()) {
      console.log(value); // Output: pomme, banane
    }
    ```

## ℹ️ Autres Propriétés et Méthodes Utiles ℹ️

* `length`: Propriété (nombre d'éléments). 📏
    ```javascript
    let couleurs = ["rouge", "vert", "bleu"];
    console.log(couleurs.length); // Output: 3
    ```
* `Array.isArray(objet)`: Vérifie si c'est un tableau. ❓➡️ ✅/❌
    ```javascript
    console.log(Array.isArray([1, 2, 3])); // Output: true
    console.log(Array.isArray({ a: 1 })); // Output: false
    console.log(Array.isArray("un tableau")); // Output: false
    ```

## 🔗 Transformation en Chaîne de Caractères 🔗

* `join(séparateur)`: Crée et retourne une nouvelle chaîne de caractères en concaténant tous les éléments d'un tableau, séparés par le `séparateur` spécifié. Si aucun séparateur n'est fourni, une virgule (`,`) est utilisée par défaut. 🧵

    ```javascript
    let fruits = ["pomme", "banane", "orange"];
    let chaineAvecVirgules = fruits.join();
    console.log(chaineAvecVirgules); // Output: "pomme,banane,orange"

    let chaineAvecTiret = fruits.join("-");
    console.log(chaineAvecTiret); // Output: "pomme-banane-orange"

    let chaineVide = fruits.join("");
    console.log(chaineVide); // Output: "pommebananeorange"
    ```


J'espère que cette version avec des exemples et des émojis rendra la compréhension et la mémorisation plus faciles ! 😊