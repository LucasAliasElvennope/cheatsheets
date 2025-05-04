# 🧮 Les opérateurs en JavaScript

## 1. 🔢 Opérateurs mathématiques de base

Opérateur|Signification|Exemple|Résultat
+|Addition ➕|2 + 3|5
-|Soustraction ➖|5 - 2|3
*|Multiplication ✖️|4 * 3|12
/|Division ➗|10 / 2|5
%|Modulo (reste) 🧮|7 % 3|1
**|Puissance 🔺|2 ** 3|8

## 2. 📝 Concaténation (coller du texte)

"Hello" + " " + "world!"  // "Hello world!"

💡 Le + fonctionne aussi pour les chaînes de texte (strings) !

## 3. 🔁 Conversion automatique

"5" - 2   // 3  ➡️ "5" est converti en nombre
"5" + 2   // "52" ➡️ concaténation (le + garde la string)

🧠 JavaScript essaie de deviner ce que tu veux faire. Ça peut être piégeux !

## 4. 🔄 Opérateurs d’affectation

Opérateur|Signification|Exemple|Équivaut à
=|Affectation simple 🎯|x = 10|
+=|Ajoute et assigne ➕|x += 5|x = x + 5
-=|Soustrait et assigne ➖|x -= 2|x = x - 2
*=|Multiplie et assigne ✖️|x *= 3|x = x * 3
/=|Divise et assigne ➗|x /= 2|x = x / 2

## 5. 📈 Incrémentation & décrémentation

Opérateur|Description|Exemple|Valeur après
++|Incrémente (+1)|x++ ou ++x|x + 1
--|Décrémente (-1)|x-- ou --x|x - 1

🧐 x++ ➡️ retourne l’ancienne valeur, puis ajoute 1
😲 ++x ➡️ ajoute 1 puis retourne la nouvelle valeur

## 6. ⚖️ Précédence (ordre des calculs)

Comme en maths, les parenthèses changent l'ordre :

```js
2 + 3 * 4     // 14 (car * avant +)
(2 + 3) * 4   // 20 (les () passent en premier)
```

🧠 Retenir : () > puissance > * / % > + -