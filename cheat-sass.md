# 🎨 **Cheat Sheet des Variables SCSS** 📝

Les **variables SCSS** permettent de stocker des valeurs comme des couleurs, des tailles ou des espacements, afin de rendre ton code plus propre et réutilisable ! Voici quelques exemples et astuces avec des emojis pour t'aider à mieux comprendre les variables SCSS ! 😎

## 1. **Déclaration des Variables** 🏷️

Les **variables** en SCSS commencent par un signe `$`, suivi du nom de la variable et de la valeur que tu veux lui attribuer.

### Exemple :
```scss
$couleur-principale: #3498db;  // Bleu 🌊
$font-principal: 'Arial', sans-serif;  // Police principale 🖋️
$taille-police: 16px;  // Taille de la police 🧐
$espace: 20px;  // Espacement entre les éléments ↔️
$border-radius: 5px;  // Rayon des bordures 🔲
```

## 2. **Utilisation des Variables** 🔄

Tu peux utiliser une variable partout dans ton fichier SCSS pour appliquer sa valeur où tu veux !
Exemple :

```scss
body {
  background-color: $couleur-principale;  // Applique la couleur principale 🌈
  font-family: $font-principal;  // Applique la police principale 🅰️
  font-size: $taille-police;  // Applique la taille de police 👀
}

h1 {
  color: darken($couleur-principale, 10%);  // Assombrit la couleur principale 🌚
  margin-bottom: $espace;  // Marge en bas 🛑
}

.button {
  border-radius: $border-radius;  // Bordure arrondie 🔄
}
```

## 3. **Types de Variables** 💡

### Couleurs 🎨

Les couleurs sont souvent des variables courantes dans SCSS !

```scss
$bleu: #3498db;  // Bleu
$rouge: #e74c3c;  // Rouge
$vert: #2ecc71;  // Vert
$gris-clair: #f4f4f4;  // Gris clair
$gris-fonce: #333;  // Gris foncé
```

### Typographie 🖋️

Déclare des variables pour la typographie pour plus de cohérence !

```scss
$font-principal: 'Arial', sans-serif;  // Police principale
$font-secondaire: 'Verdana', sans-serif;  // Police secondaire
$taille-police: 16px;  // Taille de police
$font-weight-bold: 700;  // Poids de police gras
$font-weight-normal: 400;  // Poids de police normal
```

### Espacements ↔️

Les marges et paddings sont essentiels pour espacer les éléments !

```scss
$espace-small: 10px;  // Petit espacement
$espace-medium: 20px;  // Espacement moyen
$espace-large: 40px;  // Grand espacement
$padding-standard: 15px;  // Padding standard
$margin-standard: 20px;  // Marge standard
```

### Dimensions 📐

Les tailles, largeurs et hauteurs peuvent être des variables pratiques !

```scss
$largeur-container: 1200px;  // Largeur du container
$hauteur-header: 80px;  // Hauteur du header
$hauteur-footer: 100px;  // Hauteur du footer
$radius-bordure: 10px;  // Rayon de bordure
```

## 4. **Manipulations de Couleurs** 🌈

Tu peux utiliser des fonctions pour manipuler les couleurs dans SCSS !
Fonctions de Couleurs :

    lighten() : Éclaircit une couleur

    darken() : Assombrit une couleur

    rgba() : Définit une couleur avec transparence

Exemple :

```scss
$couleur-principale: #3498db;  // Bleu principal
$couleur-claire: lighten($couleur-principale, 20%);  // Couleur plus claire ☀️
$couleur-sombre: darken($couleur-principale, 20%);  // Couleur plus sombre 🌑
$couleur-transparente: rgba($couleur-principale, 0.5);  // Couleur avec opacité 🕶️
```

5. Utilisation des Breakpoints 📱💻

Définir des variables pour les tailles d'écran permet de mieux gérer le responsive design !

```scss
$mobile: 480px;  // Petit écran (mobile)
$tablette: 768px;  // Tablette
$desktop: 1024px;  // Bureau
$grand-ecran: 1280px;  // Grand écran
```

Exemple :

```scss
@media (max-width: $mobile) {
  .container {
    padding: 10px;  // Moins de padding sur mobile 📱
  }
}
```

## 6. **Exemple Complet avec Variables SCSS** 📚

Voici un exemple complet pour voir comment toutes les variables se combinent !

```scss
// Déclaration des variables
$couleur-principale: #3498db;  // Bleu 🌊
$taille-police: 16px;  // Taille de police 🧐
$padding-standard: 15px;  // Espacement standard ↔️
$radius-bordure: 5px;  // Rayon de bordure 🔲

// Utilisation des variables dans le code
body {
  font-size: $taille-police;  // Applique la taille de la police
  background-color: $couleur-principale;  // Applique la couleur de fond
  padding: $padding-standard;  // Applique l'espacement
}

button {
  background-color: $couleur-principale;  // Couleur du bouton 🌈
  color: white;  // Texte blanc 🧑‍🦰
  padding: $padding-standard;  // Espacement interne
  border-radius: $radius-bordure;  // Bordures arrondies 🔄

  &:hover {
    background-color: darken($couleur-principale, 10%);  // Couleur du bouton au survol 🖱️
  }
}
```

## 7. Résumé des Principaux Types de Variables 📝

Type	Exemple	Utilisation
Couleur 🎨	$couleur-principale: #3498db;	Stocke des couleurs pour les utiliser partout
Typographie 🖋️	$taille-police: 16px;	Définit les tailles et polices de texte
Espacement ↔️	$padding-standard: 20px;	Définit les marges et paddings
Dimensions 📐	$hauteur-header: 80px;	Définit les tailles d'éléments spécifiques
Breakpoints 📱💻	$mobile: 480px;	Définit les tailles d'écran pour le responsive design
🚀 Bonne pratique : Utilise des variables pour rendre ton code plus facile à modifier, maintenir et réutiliser ! En changeant une seule variable, tout ton site peut être mis à jour ! 🎉
