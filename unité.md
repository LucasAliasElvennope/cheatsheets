# Les unités de mesure à éviter pour un affichage sur ordinateur

Parmi les différentes unités de taille en CSS, il existe des unités qui ne sont pas conseillées à utiliser pour un affichage sur un écran d’ordinateur. Vous pouvez néanmoins utiliser ces unités pour des supports haute-résolution ou bien pour les supports d’impression.

Ces unités sont les : **pt**, **cm**, **mm**, **in** et **pc** qui représentent respectivement le **« point »**, **« millimètre »**, **« centimètre »**, **« pouce »** et **« pica »**.

> **Note**: Que vous recherchiez un graphiste pour créer une affiche ou un web designer pour améliorer le design de votre site, trouvez le freelance qu’il vous faut sur [Codeur.com](https://www.codeur.com). Décrivez votre projet et recevez de nombreux devis de professionnels, gratuitement.

## Le Pixel

Le **pixel**, comme vu en introduction de cet article, est une unité **relative** à la **résolution** et à la **taille de l’écran** sur lequel il est affiché.

Cette unité, considérée comme « magique », permet un affichage net et visible, même si petite, sur n’importe quel support.

## Le Pourcentage

Cette unité notée **`%`** est **relative** à son **élément parent**. Un élément avec une taille de **50%** et qui a un élément parent avec une taille de **50px** aura alors une taille de **25px**.

Le pourcentage sera à utiliser chaque fois que vous souhaiterez définir une taille en fonction de son élément parent.

## Le `em`

Le **`em`** correspond à la **taille de la police de caractère** de l’élément en cours et si cette taille n’est pas redéfinie, alors cette taille correspondra à la taille de la police de l’élément parent. Par exemple, si la taille de la police est définie à **20px**, alors **1em** sera égal à **20px**.*
si pas d'élément parent la taille sera de **16px** (taille par défaut) donc **1em = 16px**

Cette unité peut être utilisée pour définir les **marges intérieures** (**paddings**) ou **extérieures** (**margins**) qui seront liées à la taille du texte et ainsi les redimensionner en fonction de cette dernière sur différents supports.

Ainsi, sur un grand écran, les marges seront plus grandes tout comme la taille du texte et, à l’inverse, sur un petit écran (comme un écran de smartphone), les textes seront plus petits et les marges aussi.

Vous trouverez souvent les déclarations **`margin: 1em`** et **`text-indent: 1.5em`** en CSS.

## Le `ex`

L’unité **`ex`** est une unité rarement utilisée qui permet d’exprimer des tailles relatives à l'**x-height** de la police. Le x-height est la hauteur des plus petites lettres (minuscules) d’une police.

## Le `rem`

L’unité **`rem`** variable signifiant **« root em »** reprend le principe de l’unité **`em`**, c’est-à-dire qu’elle correspond à la taille de la police d’un élément, mais cet élément est l’élément racine du document (**root**) donc police par défaut.

Ainsi, le **`rem`** permet de définir une valeur constante tout le long du document égale à la taille de la police de l’élément racine.

Cette unité peut être utilisée pour créer des éléments et propriétés CSS **responsives** puisque celle-ci s’adaptera à la taille de la police du support d’affichage.

Pour faciliter declarer la taille de police a 10px

## Les `vw` et `vh`

Les unités **`vw`** et **`vh`** sont similaires car elles correspondent au **viewport** de la fenêtre.

- **`vw`** correspondra à la **largeur** du viewport, tandis que **`vh`** se réfèrera à la **hauteur** du viewport.
- **`vw`** correspond ainsi à 1/100 de la largeur de la fenêtre et **`vh`** équivaut à 1/100 de la hauteur de la fenêtre.

Grâce à ces deux unités, vous allez pouvoir définir des tailles relatives à la taille du **viewport** de votre support d’affichage et ainsi créer facilement des éléments responsives ou par exemple un élément qui prendra toute la largeur de l’écran.

## Les `vmin` et `vmax`

Les unités **`vmin`** et **`vmax`** équivalent respectivement à **1/100** de la **dimension la plus petite** et à **1/100** de la **dimension la plus grande** du viewport.

- Les éléments avec une unité **`vmin`** s’adapteront selon la **hauteur** de la fenêtre.
- Les éléments avec une unité **`vmax`** s’adapteront selon la **largeur** de la fenêtre.

Pour un viewport ayant les dimensions suivantes : **2000px** de large et **1000px** de hauteur, une valeur de **1vmin** sera égale à **10px** et une valeur de **1vmax** équivaudra à **20px**.

## Conclusion

Il existe de nombreuses unités de taille en CSS, certaines ne seront à utiliser que pour quelques cas particuliers tels que les **pt**, **cm**, **mm**, **in** et **pc** et les autres seront à utiliser selon le besoin. Néanmoins, les **unités relatives** sont souvent plus appréciées pour leur côté **adaptable** et les unités **`rem`**, **`vh`** et **`vw`** sont de plus en plus utilisées pour leur simplicité et efficacité de gestion du **multi-support**.

L’utilisation des bonnes unités est un chapitre complexe de l’apprentissage du CSS.

Les unités nécessitent d’être choisies correctement pour avoir un affichage joli et efficace sur tout type d’écran, n’hésitez donc pas à poster une annonce gratuite sur **[Codeur.com](https://www.codeur.com)** pour trouver rapidement un freelance qui pourra vous aider à gérer correctement les tailles de police et de visuels sur votre site pour un résultat responsive.


# Pour responsive les plus important sont **vh, vm, rem,em, %**