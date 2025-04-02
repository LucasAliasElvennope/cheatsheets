# Les Combinateurs CSS

Les **combinateurs CSS** sont utilisés pour combiner des sélecteurs et cibler des éléments HTML en fonction de leur relation avec d'autres éléments.

## Types de Combinateurs

    Descendant combinator (space)

    Child combinator (>)

    Adjacent sibling combinator (+)

    General sibling combinator (~)

## Exemple HTML :

```html
<div class="container">
  <p>Premier paragraphe</p>
  <div class="box">
    <p>Deuxième paragraphe</p>
  </div>
  <p>Troisième paragraphe</p>
</div>
```

## Exemple CSS avec des combinators :

```css
/* 1. Descendant combinator (espace) : Sélectionne tous les p dans .container, peu importe leur niveau */
.container p {
  color: blue;
}

/* 2. Child combinator (>) : Sélectionne les p qui sont des enfants directs de .container */
.container > p {
  font-weight: bold;
}

/* 3. Adjacent sibling combinator (+) : Sélectionne le premier p qui suit immédiatement un .box */
.box + p {
  color: red;
}

/* 4. General sibling combinator (~) : Sélectionne tous les p qui suivent un .box, pas nécessairement immédiatement */
.box ~ p {
  font-style: italic;
}
```

## Explication des combinators :

    Descendant combinator (.container p):

        Sélectionne tous les éléments <p> qui se trouvent n'importe où dans .container, qu'ils soient enfants directs ou non.

    Child combinator (.container > p):

        Sélectionne les éléments <p> qui sont des enfants directs de .container. Dans cet exemple, seul le premier paragraphe sera sélectionné.

    Adjacent sibling combinator (.box + p):

        Sélectionne le premier élément <p> qui vient immédiatement après .box. Ici, cela sélectionne le paragraphe qui suit directement la div avec la classe .box.

    General sibling combinator (.box ~ p):

        Sélectionne tous les éléments <p> qui viennent après .box, peu importe s'ils sont immédiatement après ou non. Cela s'applique à tous les paragraphes qui suivent .box`.

## Résultat :

    Le premier paragraphe sera bleu.

    Le deuxième paragraphe sera en gras.

    Le troisième paragraphe sera en rouge car il suit directement .box.

    Le troisième paragraphe sera aussi en italique car il suit .box, mais pas nécessairement immédiatement.