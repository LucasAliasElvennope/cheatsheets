# 🎯 Cheat Sheet Architecture SCSS 7-1

> 📁 Une structure claire pour organiser ton CSS avec méthode et propreté.

---

## 📂 1. abstracts/ (`_variables.scss`, `_mixins.scss`, `_functions.scss`, `_placeholders.scss`)
💡 **Contient les outils SCSS réutilisables** (pas de code CSS direct ici)

| Fichier | À quoi ça sert |
|--------|----------------|
| `_variables.scss` 🎨 | Définir toutes tes couleurs, tailles, polices |
| `_mixins.scss` 🧩 | Regrouper des blocs de propriétés CSS réutilisables |
| `_functions.scss` 🧮 | Fonctions SCSS personnalisées (ex: calculs, couleurs) |
| `_placeholders.scss` 📌 | Selecteurs `%nom` à étendre avec `@extend` |

---

## 📂 2. base/ (`_reset.scss`, `_typography.scss`, `_base.scss`)
🛠️ **Gère les styles globaux**

| Fichier | À quoi ça sert |
|--------|----------------|
| `_reset.scss` 🔄 | Remise à zéro des styles par défaut navigateur |
| `_base.scss` 📋 | Styles HTML de base (`body`, `a`, `ul`, etc.) |
| `_typography.scss` ✍️ | Polices, tailles de texte, interlignages |

---

## 📂 3. components/ (`_button.scss`, `_card.scss`, etc.)
🧱 **Petits modules réutilisables partout**

| Exemple de fichier | À quoi ça sert |
|--------------------|----------------|
| `_button.scss` 🔘 | Styles de boutons |
| `_form.scss` 📝 | Champs de formulaires |
| `_badge.scss` 🎫 | Étiquettes visuelles |
| `_navbar.scss` 🍔 | Barre de navigation |

---

## 📂 4. layout/ (`_header.scss`, `_footer.scss`, `_grid.scss`, etc.)
📐 **Organisation des grandes sections de la page**

| Fichier | À quoi ça sert |
|--------|----------------|
| `_header.scss` 🧢 | En-tête du site |
| `_footer.scss` 👣 | Pied de page |
| `_grid.scss` 🧮 | Système de grille ou disposition générale |
| `_sidebar.scss` 📚 | Barres latérales si besoin |

---

## 📂 5. pages/ (`_home.scss`, `_gallery.scss`, etc.)
📄 **Styles spécifiques à certaines pages**

| Exemple | À quoi ça sert |
|---------|----------------|
| `_home.scss` 🏡 | Page d’accueil |
| `_about.scss` 👩‍💼 | Page "À propos" |
| `_blog.scss` ✍️ | Page blog |
| `_contact.scss` 📞 | Page contact |

---

## 📂 6. themes/ (`_theme.scss`, `_dark.scss`, etc.)
🎨 **Thèmes alternatifs (sombre, clair, pastel...)**

| Fichier | À quoi ça sert |
|--------|----------------|
| `_theme.scss` | Thème par défaut |
| `_dark.scss` 🌙 | Thème sombre |
| `_baby.scss` 👶 | Thème bébé pastel, doux |

---

## 📂 7. vendors/ (`_bootstrap.scss`, `_normalize.scss`, etc.)
📦 **Fichiers de bibliothèques tierces (externes)**

| Fichier | À quoi ça sert |
|--------|----------------|
| `_normalize.scss` 🧹 | Normalisation des styles navigateurs |
| `_swiper.scss` | Librairie carousel par exemple |

---

## 📂 root file: `main.scss`
🚀 **Le fichier central qui importe tout avec `@use` ou `@import`**

```scss
// Exemple :
@use 'abstracts/variables';
@use 'base/base';
@use 'layout/header';
@use 'components/button';
@use 'pages/home';
```


