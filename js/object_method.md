# 🛠️ Les Méthodes d'Objet

Les objets peuvent avoir des méthodes, qui sont des fonctions définies comme propriétés de l'objet. Ces fonctions permettent à l'objet d'agir, par exemple :

```javascript
let user = {
  name: "John",
  sayHi() {
    alert("Hello!");
  }
};

user.sayHi(); // Affiche "Hello!"
```

## 🔑 Le mot-clé this

    this fait référence à l'objet avant le point dans les méthodes.

    Par exemple, dans user.sayHi(), this fait référence à user :

```javascript
let user = {
  name: "John",
  sayHi() {
    alert(this.name); // Affiche "John"
  }
};
user.sayHi();
```

## ⚡ Syntaxe Abrégée des Méthodes

Les méthodes peuvent aussi être écrites plus succinctement sans le mot-clé function :

```javascript
let user = {
  sayHi() { alert("Hello"); }
};
```

## 🌀 Le comportement de this

    this peut changer selon le contexte d'appel.

    Exemple avec deux objets :

```javascript
let user = { name: "John" };
let admin = { name: "Admin" };

function sayHi() {
  alert(this.name);
}

user.f = sayHi;
admin.f = sayHi;

user.f(); // Affiche "John"
admin.f(); // Affiche "Admin"
```

## ❌ Appel sans Objet

Si this est utilisé sans un objet, this est undefined en mode strict, ou l'objet global (window) en mode non strict :

```javascript
function sayHi() {
  alert(this); // undefined (en mode strict)
}
sayHi();
```

## 🎯 Fonctions Fléchées et this

Les fonctions fléchées ne possèdent pas leur propre this. Elles utilisent le this du contexte extérieur :

```javascript
let user = {
  firstName: "Ilya",
  sayHi() {
    let arrow = () => alert(this.firstName);
    arrow(); // Affiche "Ilya"
  }
};
user.sayHi();
```

## 📋 Résumé

    Les méthodes sont des fonctions dans les objets.

    this fait référence à l'objet lors de l'appel d'une méthode.

    Les fonctions fléchées n'ont pas leur propre this; elles héritent de l'extérieur.

