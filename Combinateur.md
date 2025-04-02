# Les Combinateurs CSS

Les **combinateurs CSS** sont utilisés pour combiner des sélecteurs et cibler des éléments HTML en fonction de leur relation avec d'autres éléments.

## Types de Combinateurs

### 1. Combinateur Descendant (`E F`)

Ce combinateur cible un élément **F** qui est un descendant de l'élément **E** (enfant, petit-enfant, etc.).

**Exemple :**

```html
<ul>
  <li>Item 1</li>
  <li>Item 2
    <ol>
      <li>Item 2-1</li>
      <li>Item 2-2</li>
    </ol>
  </li>
  <li>Item 3</li>
</ul>
```

```css
ul li {
  background: red;
}
```

### 2. Combinateur Enfant (E > F)

Ce combinateur cible un élément F qui est un enfant direct de l'élément E.

**Exemple :**

```html
<ul>
  <li>Item 1</li>
  <li>Item 2
    <ol>
      <li>Item 2-1</li>
      <li>Item 2-2</li>
    </ol>
  </li>
  <li>Item 3</li>
</ul>
```

```css
ul > li {
  background: red;
}
```

### 3. Combinateur Adjacent (E + F)

Ce combinateur cible un élément F qui suit immédiatement un élément E.

**Exemple :**

```html
<h1>Heading</h1>
<p>Paragraph 1</p>
<p>Paragraph 2</p>
<p>Paragraph 3</p>
```

```css
h1 + p {
  font-size: 1.5em;
}
```

### 4. Combinateur Frères Généraux (E ~ F)

Ce combinateur cible tous les éléments F qui suivent un élément E dans le même conteneur.

**Exemple :**

```html
<h1>Heading</h1>
<p>Paragraph 1</p>
<p>Paragraph 2</p>
<p>Paragraph 3</p>
```

```css
h1 ~ p {
  color: blue;
}
```
