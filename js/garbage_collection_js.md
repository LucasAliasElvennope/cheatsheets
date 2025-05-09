# 🧹 Garbage Collection en JavaScript — Version Débutant

## Qu'est-ce que le Garbage Collection ?

Quand tu crées des objets, des fonctions, ou des tableaux en JavaScript, tout ça prend de la mémoire 💾.
Heureusement, tu n’as pas besoin de gérer cette mémoire toi-même : le moteur JavaScript s’en occupe automatiquement grâce à un système appelé Garbage Collector.

## 📌 L’idée principale : l’accessibilité

🔗 Le GC garde en mémoire tout ce qui est encore accessible.
S’il ne trouve aucun moyen d’atteindre un objet => 🗑️ il le supprime de la mémoir

## 🌱 Les « racines » (roots)

Ce sont les points de départ à partir desquels le moteur JS cherche ce qui est encore utilisé :

- Les variables globales

- Les fonctions en cours d’exécution

- Les paramètres de fonctions actives

Etc.

➡️ Si un objet est relié directement ou indirectement à une racine, il est conservé.

### 🧪 Exemple simple

```js
let user = { name: "Lucas" }; // 👉 accessible (grâce à la variable user)

user = null; // ❌ plus aucune référence à l’objet => supprimé par le GC
```

### 🧩 Deux références

```js
let user = { name: "Lucas" };
let admin = user;

user = null; // 👈 l’objet est encore accessible via admin ✅
admin = null; // ❌ plus aucune référence => supprimé
```

### 💑 Objets liés entre eux

```js
function marry(man, woman) {
  woman.husband = man;
  man.wife = woman;

  return { father: man, mother: woman };
}

let family = marry({ name: "John" }, { name: "Ann" });

Même si John et Ann se référencent l’un l’autre, ils peuvent être supprimés si la seule référence depuis les racines (ici family) est supprimée :

family = null; // ❌ toute la "famille" devient inaccessible => supprimée

```

## 🔍 Comment ça marche techniquement ? (simplifié)

L’algorithme utilisé s’appelle mark-and-sweep :

- Il marque les objets accessibles depuis les racines.

- Il suit leurs références pour marquer d’autres objets.

- À la fin, tout ce qui n’est pas marqué est supprimé 🗑️.

Imagine un seau de peinture que tu verses sur les racines : tout ce que la peinture touche est conservé, le reste est effacé !

## ⚠️ Ce qu’il faut retenir

- ✅ Tu n’as rien à faire, le GC travaille automatiquement.

- ❌ Un objet non accessible depuis les racines est supprimé.

- 🔗 Même des objets connectés entre eux peuvent être supprimés s’ils ne sont plus reliés à une racine.

- 🧠 Bien comprendre ça t’aide à éviter les fuites de mémoire (quand des objets restent bloqués inutilement en mémoire).