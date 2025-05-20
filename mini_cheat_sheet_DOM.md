
# Mini Cheat-Sheet : Écouteurs d’événements & Sélecteurs DOM 🔥

---

### 1️⃣ `addEventListener` 🎧

**Utilité :** Écouter un événement (clic, touche, etc.) sur un élément HTML.

```js
element.addEventListener('click', function() {
  console.log("Clic détecté !");
});
```

- Écoute l’événement `'click'` sur `element`  
- Exécute la fonction quand clic reçu

---

### 2️⃣ `document.getElementById` 🆔

**Utilité :** Sélectionner un élément unique par son `id`.

```js
const btn = document.getElementById('next');
```

- Récupère l’élément avec `id="next"`  
- Retourne un seul élément

---

### 3️⃣ `for` loop 🔄

**Utilité :** Répéter des actions plusieurs fois (ex: parcourir un tableau).

```js
for (let i = 0; i < slides.length; i++) {
  slides[i].style.display = 'none';  // Cache chaque slide
}
```

- Initialise `i = 0`  
- Continue tant que `i < slides.length`  
- Incrémente `i` à chaque tour

---

### 4️⃣ `.style` 🎨

**Utilité :** Modifier les styles CSS d’un élément via JavaScript.

```js
element.style.display = 'none';  // Cache l’élément
element.style.color = 'red';     // Change la couleur du texte
```

- Manipule les propriétés CSS inline

---

### 5️⃣ `.style.display` 👁️‍🗨️

**Utilité :** Contrôler la visibilité et le type d’affichage d’un élément.

- `none` → cache l’élément  
- `block` → affiche en bloc (nouvelle ligne)  
- `inline` → affiche en ligne (comme du texte)  

```js
element.style.display = 'block';  // Affiche l’élément
element.style.display = 'none';   // Cache l’élément
```

---

### 6️⃣ `document.querySelectorAll` 🔎

**Utilité :** Sélectionner **tous** les éléments correspondant à un sélecteur CSS.

```js
const items = document.querySelectorAll('.item');

items.forEach(item => {
  item.style.color = 'blue';  // Change la couleur de tous les éléments '.item'
});
```

- Retourne une liste (NodeList) d’éléments  
- Parcourable avec `forEach` ou boucle `for`

---
