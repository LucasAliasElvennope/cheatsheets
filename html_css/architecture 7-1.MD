# 🎀 SCSS 7-1 Architecture pour Site Photo Bébé 👶📸

Bienvenue dans le projet SCSS avec l’architecture **7-1** (💡 7 dossiers + 1 fichier principal).  
Cette structure permet une organisation **claire, modulaire et évolutive** du style de ton site 💻✨.

---

## 📁 Dossiers & Fichiers

### `scss/` → Le cœur du style ❤️

- `main.scss` – 🧵 Le fichier principal qui importe tout le reste.
- `abstracts/` – ⚙️ Variables, mixins, fonctions (outils globaux).
- `base/` – 🌱 Reset, typographies et styles de base.
- `components/` – 🧩 Boutons, formulaires, sliders, etc.
- `layout/` – 🧱 Header, footer, navigation, grille...
- `pages/` – 📄 Styles spécifiques à chaque page.
- `themes/` – 🎨 Thèmes visuels (clair/sombre, etc).
- `vendors/` – 📦 Fichiers de bibliothèques externes.

---

## 🧠 Contenu des fichiers

### `abstracts/`
| Fichier | Rôle |
|--------|------|
| `_variables.scss` | 🎨 Couleurs, typographies, espacements... |
| `_mixins.scss` | ♻️ Mixins SCSS (responsive, raccourcis...) |
| `_functions.scss` | 🧮 Fonctions SCSS personnalisées |

---

### `base/`
| Fichier | Rôle |
|--------|------|
| `_reset.scss` | 🔄 Reset CSS universel |
| `_base.scss` | 🧍 Styles globaux du `body`, des images... |
| `_typography.scss` | ✍️ Titres, paragraphes, liens... |

---

### `components/`
| Fichier | Rôle |
|--------|------|
| `_buttons.scss` | 🔘 Boutons stylisés |
| `_form.scss` | 📝 Champs de formulaires |
| `_carousel.scss` | 🎠 (si besoin) Carrousel d’images |

---

### `layout/`
| Fichier | Rôle |
|--------|------|
| `_header.scss` | ⬆️ En-tête du site |
| `_footer.scss` | ⬇️ Pied de page |
| `_navigation.scss` | 📑 Menu et nav |
| `_grid.scss` | 🔲 Système de grille avec CSS Grid |

---

### `pages/`
| Fichier | Rôle |
|--------|------|
| `_home.scss` | 🏡 Page d’accueil |
| `_about.scss` | 🙋 À propos |
| `_gallery.scss` | 🖼️ Galerie |
| `_contact.scss` | 📬 Contact |

---

### `themes/`
| Fichier | Rôle |
|--------|------|
| `_theme.scss` | 🎭 Thèmes personnalisés (clair/sombre, etc.) |

---

### `vendors/`
| Fichier | Rôle |
|--------|------|
| `_bootstrap.scss` | 🚀 Import/override de Bootstrap ou autres libs |

---

## ✨ Exemple d’import dans `main.scss`

```scss
@use 'abstracts/variables';
@use 'base/reset';
@use 'layout/header';
@use 'components/buttons';
@use 'pages/home';
```
