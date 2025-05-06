# 🏷️ 1. 💡 Nommage de variables


|🔤 Description|✅ Nom de variable proposé|
|---|---|
|Ton prénom	|let prenom = "Lucas";|
|Ton âge	|let age = 20;|
|Si tu es développeur	|let estDeveloppeur = true;|
|Langage préféré	|let langageFavori = "JavaScript";|
|Score dans un jeu	|let scoreJeu = 1500;|

# 📦 2. 🔍 Identifier les types de données

```js
let nom = "Sarah";               // ✅ string
let age = 25;                    // ✅ number
let enFormation = true;         // ✅ boolean
let ville;                      // ✅ undefined
let skills = ["HTML", "CSS", "JS"]; // ✅ object (tableau → type object)
```

#🔢 3. 🧮 Exercices sur les opérateurs

```js
5 + 3           // ✅ 8
"Hello" + "World" // ✅ "HelloWorld" (concaténation de 2 strings)
10 - 2 * 3      // ✅ 4 (priorité : 2 * 3 = 6 → 10 - 6)
7 % 2       // ✅ 1 (reste de 7 ÷ 2)

let x = 4; 
x += 2;         // ✅ x vaut maintenant 6
```

# 🔍 4. ✅ Comparaisons

```js
5 > 3           // ✅ true
4 == "4"        // ✅ true (égalité "souple", conversion de type)
4 === "4"       // ✅ false (égalité stricte, types différents)
10 != 5         // ✅ true
false == 0      // ✅ true (car false est converti en 0)
```

# 💡 Bonus : types et logique

```js
typeof ("5" + 1)      // ✅ "string" (concaténation → "51")
typeof (5 + "1")      // ✅ "string" (concaténation → "51")
typeof (5 - "1")      // ✅ "number" (soustraction → 4)
typeof (true + 1)     // ✅ "number" (true → 1, donc 1 + 1 = 2)
typeof (null + 1)     // ✅ "number" (null → 0, donc 0 + 1 = 1)
```

