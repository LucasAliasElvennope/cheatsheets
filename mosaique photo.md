# 🧱 Cheat Sheet — Galerie Mosaïque Responsive (Méthode column-count)

Crée une galerie fluide, sans JS, où les images se placent automatiquement dans une mosaïque 🖼️✨

---

## 📂 HTML Structure

```html
<section class="masonry">
  <img src="img1.jpg" alt="photo 1">
  <img src="img2.jpg" alt="photo 2">
  <img src="img3.jpg" alt="photo 3">
  <!-- ➕ Ajoute autant d'images que tu veux -->
</section>

🎨 SCSS / CSS


```scss
.masonry {
  column-count: 3;           // 🧱 Nombre de colonnes
  column-gap: 1rem;          // ↔️ Espace entre les colonnes
  padding: 1rem;             // 📦 Marge intérieure
}
```

```scss
.masonry img {
  width: 100%;               // 🖼️ Prend toute la largeur de sa colonne
  margin-bottom: 1rem;       // ⬇️ Espace entre les images
  break-inside: avoid;       // ❌ Évite qu’une image soit coupée
  border-radius: 10px;       // 🔵 Coins arrondis
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1); // 🌫️ Ombre douce
  transition: transform 0.3s ease; // 🎞️ Animation au survol
}

.masonry img:hover {
  transform: scale(1.03);    // 🔍 Petit zoom au survol
}
```

📱 Responsive (💡 optionnel mais conseillé)

```scss
@media screen and (max-width: 768px) {
  .masonry {
    column-count: 2;         // 📱 Moins de colonnes sur tablette
  }
}

@media screen and (max-width: 480px) {
  .masonry {
    column-count: 1;         // 📱 Une seule colonne sur mobile
  }
}
```

✅ Avantages

    🔁 Ajout facile d’images (elles se placent automatiquement)

    📐 Pas de tailles fixes (les hauteurs sont naturelles)

    🚫 Aucun JS requis

    💨 Ultra léger et rapide

    📷 Parfait pour galeries d’art, portfolios, photos de bébé 👶 etc.
