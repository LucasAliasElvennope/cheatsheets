
# 🧠 Mini Cheat-Sheet — `<=`, `>=`, `=>` en JavaScript

## 🔸 `<=` — Inférieur ou égal à  
👉 Vérifie si la valeur de gauche est **plus petite ou égale** à celle de droite.

```javascript
5 <= 10  // ✅ true
10 <= 10 // ✅ true
15 <= 10 // ❌ false
```
📌 **Utilisé dans les comparaisons (conditions `if`, boucles, etc.)**

---

## 🔸 `>=` — Supérieur ou égal à  
👉 Vérifie si la valeur de gauche est **plus grande ou égale** à celle de droite.

```javascript
10 >= 5   // ✅ true
10 >= 10  // ✅ true
5 >= 10   // ❌ false
```
📌 **Autre opérateur de comparaison logique.**

---

## 🔸 `=>` — Fonction fléchée (arrow function)  
👉 Sert à **définir une fonction rapide et concise**.

```javascript
const saluer = (nom) => console.log("Salut " + nom);
saluer("Lucas"); // 👋 Salut Lucas
```

💡 Elle signifie **"prend ceci => retourne cela"**.

---

## ⚠️ À ne pas confondre :

| Symbole | Signification                    | Type             |
|---------|----------------------------------|------------------|
| `<=`    | Inférieur ou égal à              | Comparaison 🔍   |
| `>=`    | Supérieur ou égal à              | Comparaison 🔍   |
| `=>`    | Fonction fléchée (arrow function)| Déclaration 🛠️ |
