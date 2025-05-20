# 📚 Mini Cheat-Sheet JS : Méthodes Essentielles 🚀

## 1. getElementById() 🎯

Description : Sélectionne un élément HTML par son attribut id unique. C'est votre go-to pour choper un élément précis !
**Syntaxe :** `document.getElementById('votreID')`
**Exemple :**

```html
<div id="monDiv">Salut !</div>
<script>
  const monDiv = document.getElementById('monDiv');
  console.log(monDiv); // Affiche l'élément <div id="monDiv">
</script>
```

## 2. addEventListener() 👂

Description : Attache une fonction (un "écouteur") à un événement spécifique (clic, survol, etc.) sur un élément. Super utile pour rendre vos pages interactives !
**Syntaxe :** `element.addEventListener('typeEvenement', fonctionAGerer)`
**Exemple :**

```html
<button id="monBouton">Clique-moi !</button>
<script>
  const monBouton = document.getElementById('monBouton');
  monBouton.addEventListener('click', () => {
    alert('Bouton cliqué !');
  });
    </script>
```

## 3. createElement() ✨

Description : Crée un nouvel élément HTML en mémoire. Il n'est pas encore sur la page, il faut l'ajouter avec appendChild() ou insertBefore().
**Syntaxe :** `document.createElement('nomDeLaBalise')`
**Exemple :**

```javascript
const nouveauParagraphe = document.createElement('p');
console.log(nouveauParagraphe); // Affiche <p></p>
```

## 4. textContent 📝

Description : Permet de récupérer ou de définir le contenu textuel d'un nœud et de ses descendants. Il ne tient pas compte du balisage HTML.
**Syntaxe (récupérer) :** `element.textContent`
**Syntaxe (définir) :** `element.textContent = 'Nouveau texte'`
**Exemple :**

```html
<div id="monElement">Texte **original**</div>
<script>
  const monElement = document.getElementById('monElement');
  console.log(monElement.textContent); // Affiche "Texte original"
  monElement.textContent = 'Le texte a changé !';
  console.log(monElement.textContent); // Affiche "Le texte a changé !"
</script>
```

## 5. appendChild() 🌱

Description : Ajoute un nœud comme dernier enfant d'un nœud parent spécifié. C'est comme mettre un nouvel élément à la fin d'une liste.
**Syntaxe :** `parent.appendChild(enfant)`
**Exemple :**

```html
<div id="conteneur"></div>
<script>
  const conteneur = document.getElementById('conteneur');
  const nouveauDiv = document.createElement('div');
  nouveauDiv.textContent = 'Je suis un nouvel enfant !';
  conteneur.appendChild(nouveauDiv); // Ajoute <div id="conteneur"><div>Je suis un nouvel enfant !</div></div>
    </script>
```

## 6. innerHTML 🎨

Description : Permet de récupérer ou de définir tout le contenu HTML (y compris les balises) à l'intérieur d'un élément. Attention, peut être une faille de sécurité si vous insérez du contenu utilisateur non filtré !
**Syntaxe (récupérer) :** `element.innerHTML`
**Syntaxe (définir) :** `element.innerHTML = '<p>Nouveau <strong>HTML</strong></p>'`
**Exemple :**

```html
<div id="zoneContenu"></div>
<script>
  const zoneContenu = document.getElementById('zoneContenu');
  zoneContenu.innerHTML = '<h1>Titre ajouté</h1><p>Un paragraphe avec du <em>texte</em>.</p>';
  console.log(zoneContenu.innerHTML); // Affiche le HTML inséré
</script>
```

