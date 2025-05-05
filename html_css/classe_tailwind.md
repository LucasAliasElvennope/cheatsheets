# 🌈 Cheat Sheet Tailwind CSS

Voici une petite référence des classes Tailwind CSS avec des explications et quelques illustrations.

## 🚀 **Conteneur (Container)**

### `.container`

La classe `.container` est utilisée pour définir un conteneur avec une largeur maximale et un alignement central.

```html
<section class="container mx-auto">
  <p>Contenu centré avec une largeur maximale !</p>
</section>
```

---

## 🎨 **Couleurs (Colors)**

### `.bg-{color}`

La classe `.bg-{color}` permet de définir la couleur de fond d'un élément.

```html
<article class="bg-blue-500 p-4 text-white">
  <p>Ce texte a un fond bleu et une couleur de texte blanche !</p>
</article>
```

**Dans la classe class="bg-blue-500 p-4 text-white" de Tailwind CSS, les valeurs 500 et 4 ont des significations spécifiques :**

# 1. bg-blue-500 :

Cela définit la couleur de fond de l'élément.

    bg-blue fait référence à une couleur bleue.

    Le 500 fait partie du système de couleurs de Tailwind, qui utilise des échelles numérotées pour indiquer l'intensité ou la saturation de la couleur.

        Plus le nombre est élevé (ex. 500, 600, 700), plus la couleur est saturée et foncée.

        Plus le nombre est bas (ex. 100, 200), plus la couleur est claire.

Donc, bg-blue-500 applique un bleu de moyenne intensité.

# 2. p-4 :

Cela définit le padding (espace intérieur) de l'élément.

    Le p signifie padding.

    Le 4 indique que le padding est de 1rem (16px) autour de l'élément. Dans Tailwind, les tailles de padding (et de marges) suivent un système basé sur des valeurs prédéfinies :

        p-1 correspond à 0.25rem (4px),

        p-2 à 0.5rem (8px),

        p-3 à 0.75rem (12px),

        p-4 à 1rem (16px), etc.

Ainsi, p-4 ajoute un espace intérieur de 16px de chaque côté (haut, bas, gauche et droite) de l'élément. 

---

### .text-{color}

La classe `.text-{color}` change la couleur du texte.

```html
<article class="text-red-500">
  <p>Ce texte est rouge !</p>
</article>
```

**Dans la classe class="text-red-500" de Tailwind CSS, la valeur 500 a des significations spécifiques :**

---

## **🔥 Espacement (Spacing)**

### `.p-{size}`

Utilisez la classe .p-{size} pour définir l'espace intérieur (padding) autour d'un élément.

<section class="p-4">
  <p>Ce div a un padding de 4 (16px) autour de son contenu.</p>
</section>

### `.m-{size}`

La classe .m-{size} définit les marges extérieures (margins) autour d'un élément.

<section class="m-4">
  <p>Ce div a une marge de 4 (16px) autour de lui.</p>
</section>

---

## **💡 Typographie (Typography)**

### `.font-{family}`

La classe .font-{family} définit la police de caractère.

<article class="font-sans">
  <p>Ce texte utilise la police sans-serif !</p>
</article>

### `.text-{size}`

La classe .text-{size} change la taille du texte.

<article class="text-lg">
  <p>Texte en taille large !</p>
</article>

**Explication de text-lg :**

    text- : C'est un préfixe utilisé pour indiquer que l'on veut définir la taille du texte.

    lg : Cela correspond à une taille de texte spécifique dans le système de tailles de Tailwind CSS. Plus précisément, lg signifie "large".

**Dans Tailwind, les tailles de texte sont définies avec des valeurs comme suit :**

    text-xs : très petit (extra small)

    text-sm : petit (small)

    text-base : taille par défaut (généralement 1rem ou 16px)

    text-lg : grand (large)

    text-xl : extra large

    text-2xl : 2 fois plus grand qu'xl, etc.

**Taille précise :**

    text-lg correspond à une taille de texte de 1.125rem, soit 18px (en fonction de la taille de la police par défaut).

**Donc, text-lg applique une taille de texte légèrement plus grande que la taille par défaut (qui est généralement text-base ou 16px).**

---

## 🖼 Images

### `.rounded-full`

Utilisez cette classe pour donner une bordure arrondie à vos images et obtenir un effet de cercle.

<aside>
  <img src="image.jpg" class="rounded-full w-32 h-32" alt="Image ronde">
</aside>

**Note :** Ajustez w-32 et h-32 pour ajuster la taille de l'image.

### `.rounded-full`

    rounded : C’est le préfixe pour définir les bords arrondis.

    full : Cela signifie que les coins sont complètement arrondis, jusqu'à former un cercle parfait (si la largeur et la hauteur sont égales).

    🟢 Utilisation typique : pour rendre une image ou un bouton circulaire.

    ⚠️ Important : Pour que rounded-full fasse un vrai cercle, l’élément doit être carré (w = h).

### 📏 w-32 (width)

    w-32 définit la largeur de l’élément.

    En Tailwind, w-32 correspond à 8rem = 128 pixels.

### 📏 h-32 (height)

    h-32 définit la hauteur de l’élément.

    Pareil que w-32, h-32 = 8rem = 128 pixels.

**🔍 Résumé visuel :**

| Classe | Signification |
| --- | --- |
| rounded-full | Bords totalement arrondis (cercle) |
| w-32 | Largeur : 128px |
| h-32 | Hauteur : 128px |

**🖼 Exemple :**

```html
<img src="avatar.jpg" class="rounded-full w-32 h-32" alt="Avatar circulaire">
```

---

## 🔄 Flexbox

### `.flex`

Cette classe active le modèle Flexbox, vous permettant de contrôler l'alignement et la disposition des éléments à l'intérieur d'un conteneur.

<section class="flex space-x-4">
  <div class="bg-green-300 p-2">Item 1</div>
  <div class="bg-green-300 p-2">Item 2</div>
</section>

**✅ 1. flex**

    Cette classe transforme l’élément en conteneur Flexbox.

    Cela active le modèle flexible pour organiser les éléments enfants horizontalement par défaut (dans le sens de la ligne).

**➡️ Cela signifie que les enfants de ce conteneur seront affichés côte à côte (comme en display: flex en CSS classique).**

**✅ 2. space-x-4**

    Cette classe ajoute un espacement horizontal (dans l'axe X) entre les éléments enfants.

    Le 4 correspond à une valeur dans l’échelle Tailwind → 1rem = 16px.

**➡️ Cela ne met pas de marge sur les côtés extérieurs, mais ajoute un espace de 16px entre chaque enfant (le premier et le dernier n'ont pas d'espace autour d'eux).** 

| Classe | Rôle |
| --- | --- |
| flex | Active Flexbox (affichage en ligne par défaut) |
| space-x-4 | Ajoute 16px entre les enfants (horizontalement) |

---

## 🌟 Effets et Animations

### `.transition`

Utilisez cette classe pour ajouter des transitions douces sur vos éléments.

```html
<button class="bg-blue-500 text-white p-4 transition duration-300 ease-in-out transform hover:bg-blue-700 hover:scale-110">
  Survoler pour agrandir !
</button>
```

### .transition

    Active les transitions CSS (animations douces).

    Par défaut, ça applique la transition sur toutes les propriétés modifiables (comme la couleur, la taille, la position, etc.)

### .duration-300

    Définit la durée de l’animation : ici 300 ms (0.3s).

    Tu peux l’ajuster (duration-100, duration-500, etc.).

### .ease-in-out

    Définit la fonction de timing (la manière dont l’animation s’accélère ou ralentit).

    ease-in-out = commence lentement ➡ accélère ➡ finit lentement.

### .transform

    Permet d’utiliser des transformations CSS (comme scale, rotate, translate, etc.).

    Obligatoire pour que hover:scale-110 fonctionne.

### .hover:bg-blue-700

    Change la couleur de fond au survol (hover).

    Ici : devient bleu foncé (blue-700) quand on survole.

### .hover:scale-110

    Applique un zoom (agrandissement) de 110% lors du survol.

    Combiné avec transition, ça donne un effet de zoom fluide. 

--- 

## `🏠 Disposition (Layout)`

### .grid

La classe .grid permet de créer une grille avec des colonnes et des rangées.

```html
<section class="grid grid-cols-3 gap-4">
  <div class="bg-yellow-200 p-4">Colonne 1</div>
  <div class="bg-yellow-200 p-4">Colonne 2</div>
  <div class="bg-yellow-200 p-4">Colonne 3</div>
</section>
```

### .grid

    Active le système de grille CSS (display: grid).

    Ça transforme l'élément en un conteneur de grille.

### .grid-cols-3

    Crée 3 colonnes égales dans ta grille.

    Chaque élément enfant prendra une colonne (jusqu'à 3 par ligne).

    Tailwind propose jusqu’à grid-cols-12 par défaut, pour des grilles plus fines.

    📦 Exemple :

```html
<div class="grid grid-cols-3">
  <div>Col 1</div>
  <div>Col 2</div>
  <div>Col 3</div>
  <div>Col 4</div> <!-- ira à la ligne -->
</div>
```

### .gap-4

    Définit un espacement uniforme entre toutes les colonnes et les rangées (horizontal et vertical).

    gap-4 = 1rem (16px) d’espace.

    Tu peux aussi utiliser :

        gap-x-4 : uniquement entre les colonnes.

        gap-y-4 : uniquement entre les rangées.

### 🎯 Résultat combiné :

Tu obtiens une grille de 3 colonnes avec un espace de 16px entre chaque case, peu importe qu’elle soit en ligne ou en colonne.

```html
div class="grid grid-cols-3 gap-4">
  <div class="bg-red-200 p-4">1</div>
  <div class="bg-green-200 p-4">2</div>
  <div class="bg-blue-200 p-4">3</div>
  <div class="bg-yellow-200 p-4">4</div>
</div>
```

### 👉 Ici :

    Les divs 1 à 3 sont côte à côte (1 ligne, 3 colonnes).

    Le 4 passe à la ligne suivante (comme un nouveau rang).

### 📝 Résumé :

| Classe | Fonction |
| --- | --- |
| grid | Active le système de grille |
| grid-cols-3 | Crée 3 colonnes |
| gap-4 | Met 16px d’espace entre toutes les cases |

--- 

## `📱 Responsive Design`

Tailwind facilite la gestion des tailles d'écran avec les préfixes suivants :

    .sm: pour petits écrans (640px+)

    .md: pour écrans moyens (768px+)

    .lg: pour écrans larges (1024px+)

    .xl: pour écrans très larges (1280px+)

### Exemple :

```html
<section class="bg-red-500 p-4 sm:bg-blue-500 md:bg-green-500">
  <p>Le fond change en fonction de la taille de l'écran !</p>
</section>
```


