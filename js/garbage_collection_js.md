
# 📚 Garbage Collection (GC) en JavaScript

## 1. C'est quoi le Garbage Collection (GC)?

Le Garbage Collection (GC) est un processus automatique dans JavaScript qui libère de la mémoire en supprimant les objets et données inaccessibles (c’est-à-dire ceux dont il n’existe plus de références actives).

## 2. Concept clé : Accessibilité

Le GC se base sur l’accessibilité des objets en mémoire. Un objet est accessible si tu peux y accéder depuis une racine (root) par le biais d’une variable ou d’une référence.

## 3. Les racines (roots) 🌱

Les racines sont des points d'accès toujours accessibles par défaut :

- Variables globales : Déclarées en dehors des fonctions.

- Variables locales : Déclarées dans une fonction en cours d’exécution.

- Paramètres de fonction : Ceux passés à une fonction.

- Le call stack : La pile d’exécution actuelle.

### Exemple :

```javascript
let globalVar = "Hello"; // racine
function test() {
  let localVar = "World"; // racine à l'intérieur de la fonction
}
```

## 4. Marquer les objets accessibles 🖊️

Lors du processus GC, les objets accessibles sont marqués (ou “peints” en vert) :

- Le GC commence par marquer les racines (variables, paramètres, etc.).

- Ensuite, il suit toutes les références des objets accessibles et marque chaque objet rencontré.

### Exemple :

```javascript
let obj1 = { a: 1 };
let obj2 = { b: 2 };
obj1.next = obj2; // obj1 référence obj2, donc obj2 est accessible
```

// Si obj1 est une racine, obj2 devient aussi accessible.

## 5. Le processus "Mark-and-Sweep" 🧹

- Mark (Marquer) : Le GC marque tous les objets accessibles.

- Sweep (Balayer) : Tous les objets non marqués sont considérés comme inaccessibles et sont supprimés.

### Exemple :

```javascript
let obj1 = { a: 1 };
let obj2 = { b: 2 };
obj1.next = obj2;

obj1 = null; // Obj1 n'est plus accessible

// Si obj2 n'est plus référencé, il sera supprimé du mémoire après "sweep"
```

## 6. Objets liés (Linked Objects) 🔗

Les objets peuvent être liés entre eux. Un groupe d’objets interconnectés est vu comme un ensemble. Si tous les objets de l'ensemble deviennent inaccessibles, tout l’ensemble sera supprimé.

### Exemple :

```javascript
function createCouple() {
  let man = { name: "John" };
  let woman = { name: "Ann" };
  man.partner = woman; // Liens créés
  woman.partner = man;
  return { man, woman };
}

let couple = createCouple();
couple = null; // Tous les objets liés (man, woman) deviennent inaccessibles
```

## 7. Effet des références multiples 🔄

Si un objet a plusieurs références, il restera accessible tant que l'une des références est toujours utilisée.

### Exemple :

```javascript
let obj1 = { name: "Alice" };
let obj2 = obj1; // obj2 et obj1 réfèrent au même objet
obj1 = null; // L'objet est toujours accessible via obj2
```

## 8. La collecte générationnelle 🧬

Certains moteurs JavaScript utilisent la collecte générationnelle pour optimiser la gestion mémoire.

- Les nouveaux objets sont collectés plus fréquemment car ils ont une durée de vie courte.

- Les objets anciens (qui survivent aux premières collectes) sont moins souvent vérifiés.

Cela permet de réduire l'impact du GC sur les performances, en ne vérifiant pas constamment tous les objets.

## 9. La collecte incrémentielle 📉

Pour éviter un ralentissement visible, le GC peut être incrémental. Cela signifie qu'il divise le travail de nettoyage en petites étapes, permettant à ton programme de continuer à tourner pendant que la mémoire est nettoyée en arrière-plan.

## 10. La collecte en cas d’inactivité 💤

Le GC s’exécute souvent quand ton processeur est inactif ou lorsqu’il n’est pas utilisé pour des tâches critiques. Cela permet de ne pas affecter les performances en plein exécution de ton code.

## 11. Garbage Collection et les objets "lourds" ⚖️

Les objets lourds (avec de nombreuses propriétés, tableaux imbriqués, etc.) ne sont pas automatiquement supprimés à cause de leur taille. Ce qui compte pour le GC, c’est s'ils sont accessibles ou non.
Un objet lourd est généralement supprimé lorsqu'il devient inaccessible.

## 12. Meilleures pratiques pour éviter des fuites mémoire 💡

- Supprimer les références inutiles : Par exemple, mettre les objets à null quand tu n’en as plus besoin.

obj = null; // libère la mémoire

- Supprimer des clés d’objets ou des éléments de tableau si tu n'en as plus besoin :

- delete obj.key;
- arr.pop(); // retire un élément du tableau

## 13. Exemple complet 📝

```javascript
function createCircle(radius) {
  return { radius, area: Math.PI * radius * radius };
}

let circle1 = createCircle(10); // Crée un objet "circle1"
let circle2 = createCircle(20); // Crée un objet "circle2"

// On associe circle1 et circle2 dans un objet:
let circles = { small: circle1, large: circle2 };

// Maintenant, circle1 et circle2 sont accessibles via circles
circle1 = null; // circle1 devient inaccessible mais circle2 est toujours là.

circles = null; // Les deux objets "circle1" et "circle2" deviennent inaccessibles et seront supprimés
```

## 14. Conclusion et résumé 📌

- Le GC supprime les objets qui ne sont plus accessibles.

- Le processus utilise des racines pour déterminer ce qui reste en mémoire.

- Les objets liés entre eux sont tous supprimés si l'ensemble devient inaccessible.

- Le Garbage Collection fonctionne de manière automatique, et il est important de bien gérer les références pour éviter des fuites de mémoire.