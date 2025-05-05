# Positionnement en CSS

Le positionnement en CSS permet de contrôler l'emplacement des éléments dans le flux du document. Voici les types principaux de positionnement en CSS :

## 1. Positionnement `relative`

Le positionnement `relative` permet de déplacer un élément par rapport à sa position d'origine dans le flux du document.

```css
.element {
  position: relative;
  top: 20px; /* L'élément sera déplacé de 20px vers le bas */
}
```

## 2. Positionnement `absolute`

Le positionnement `absolute` permet de positionner un élément par rapport au pixel 0 0 de l'écran.

```css
.element {
  position: absolute;
  top: 10px;
  left: 20px;
}
```

## 3. Positionnement `fixed`

Le positionnement fixed permet de fixer un élément par rapport à la fenêtre du navigateur..

```css
.element {
  position: fixed;
  top: 0;
  left: 0;
}
```

## 4. Positionnement sticky

Le positionnement sticky permet de rendre un élément "collant". Il reste en place lorsqu'il atteint une certaine position en défilant. C'est une combinaison des positions `static` et `fixed`.

```css
.element {
  position: sticky;
  top: 0;
}
```

## 5. Combinateurs en CSS

Les combinateurs en CSS permettent de sélectionner des éléments en fonction de leur relation avec d'autres éléments dans le DOM.

### 1. Combinateur >

Sélectionne les enfants directs d'un élément spécifié.

```css
div > p {
  color: red;
}
```

### 2. Combinateur +

Sélectionne le frère immédiat suivant un élément spécifié.

```css
h1 + p {
  color: green;
}
```

### 3. Combinateur ~

Sélectionne tous les éléments frères d'un élément spécifié.

```css
h1 ~ p {
  color: blue;
}
```

### 4. Combinateur d'espace (descendant général)

Sélectionne tous les descendants d'un élément spécifié.

```css
div p {
  color: purple;
}
```

## Résumé

    Positionnement : Contrôle la position des éléments dans la page avec les valeurs relative, absolute, fixed et sticky.

    Combinateurs : Permet de sélectionner des éléments selon leur relation avec d'autres dans le DOM (>, +, ~, et espace).