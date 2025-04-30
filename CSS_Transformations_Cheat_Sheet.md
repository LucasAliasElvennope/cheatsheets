
# CSS Transformation Cheat Sheet 🌟

Les transformations CSS permettent de modifier l'apparence d'un élément sans changer sa position dans le document. Elles incluent des effets comme le zoom, la rotation, le déplacement, etc.

---

## 🖌️ **Transformations CSS (Transform)**

Les transformations les plus courantes sont :

### 1. **Zoom avec `scale()`** 🧐
Change la taille d'un élément.

```css
.element {
  transform: scale(1.2); /* Augmente la taille de 20% */
}
```

- **`scale(1)`** = taille normale.
- **`scale(1.2)`** = 20% plus grand.
- **`scale(0.8)`** = 20% plus petit.

### 2. **Rotation avec `rotate()`** 🔄
Fait tourner un élément autour de son axe.

```css
.element {
  transform: rotate(45deg); /* Rotation de 45 degrés */
}
```

- **`rotate(45deg)`** = rotation de 45 degrés dans le sens des aiguilles d'une montre.
- **`rotate(-45deg)`** = rotation de 45 degrés dans le sens inverse.

### 3. **Translation (Déplacement) avec `translate()`** ⬆️⬇️⬅️➡️
Déplace un élément dans les axes X et Y.

```css
.element {
  transform: translate(50px, 20px); /* Déplace l'élément de 50px à droite et 20px vers le bas */
}
```

- **`translate(50px, 20px)`** = déplace l'élément de 50px à droite et 20px vers le bas.
- **`translateX(50px)`** = déplace l'élément de 50px horizontalement.
- **`translateY(50px)`** = déplace l'élément de 50px verticalement.

### 4. **Inclinaison avec `skew()`** 🏗️
Incline un élément sur les axes X et Y.

```css
.element {
  transform: skew(20deg, 10deg); /* Incline de 20° sur l'axe X et de 10° sur l'axe Y */
}
```

- **`skew(20deg, 10deg)`** = inclinaison de 20° sur l'axe horizontal et 10° sur l'axe vertical.
- **`skewX(20deg)`** = inclinaison seulement sur l'axe X.
- **`skewY(10deg)`** = inclinaison seulement sur l'axe Y.

### 5. **Combinaison de transformations** 🔀
Tu peux combiner plusieurs transformations dans un seul `transform`.

```css
.element {
  transform: translate(50px, 20px) rotate(45deg) scale(1.1); /* Déplace, tourne et agrandit l'élément */
}
```

---

## 🧑‍💻 **Propriétés supplémentaires pour `:hover`**

### 6. **Effet de zoom sur une image au survol** 🖼️👀

```css
.image-container {
  display: inline-block;
}

.image-container img {
  width: 100%;
  transition: transform 0.3s ease; /* Ajoute une transition fluide */
}

.image-container:hover img {
  transform: scale(1.05); /* Zoom de l'image au survol */
}
```

- **`transition`** permet de rendre le zoom fluide.
- Le zoom ne s'applique qu'à l'**image** lorsqu'on survole son conteneur.

---

## 🛠️ **Autres astuces utiles**

### 7. **Ajout de transitions** 🌟
Pour rendre les transformations plus fluides, tu peux ajouter des transitions.

```css
.element {
  transition: transform 0.3s ease; /* Transition fluide de 0.3 secondes */
}

.element:hover {
  transform: scale(1.1); /* Applique un zoom au survol */
}
```

- **`transition: transform 0.3s ease;`** : Ajoute une transition fluide de 0.3 secondes pour les transformations.

### 8. **Éviter le "retour à la ligne" avec `break-inside: avoid`** 🚫🔙

```css
.masonry {
  column-count: 3;
  column-gap: 10px;
}

.masonry img {
  break-inside: avoid; /* Empêche une image de se couper au milieu d'une colonne */
}
```

- **`break-inside: avoid;`** évite que les images soient coupées ou brisées au milieu de la colonne dans un layout en **masonry**.

---

## 📋 **Résumé des propriétés importantes**

| Propriété          | Description                                    | Exemple                           |
|--------------------|------------------------------------------------|-----------------------------------|
| `scale()`          | Change la taille de l'élément.                 | `scale(1.1)` (agrandit de 10%)   |
| `rotate()`         | Fait pivoter l'élément.                        | `rotate(45deg)` (rotation de 45°)|
| `translate()`      | Déplace l'élément sur les axes X et Y.         | `translate(50px, 20px)` (déplacement) |
| `skew()`           | Incline l'élément sur les axes X et Y.         | `skew(20deg, 10deg)` (inclinaison)|
| `transition`       | Rend les transformations douces et fluides.    | `transition: transform 0.3s ease;` |
| `break-inside: avoid;` | Empêche les éléments de se couper dans une grille | `break-inside: avoid;`          |

