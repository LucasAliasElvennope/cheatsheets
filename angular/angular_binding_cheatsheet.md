# Angular - Lier HTML et TypeScript 🚀

## 📝 Interpolation - Afficher des données
```html
<h1>{{ message }}</h1>
<p>Bonjour {{ userName }} !</p>
<span>{{ 2 + 3 }}</span>
```
**💡 À retenir :** Les doubles accolades `{{ }}` permettent d'afficher des variables TypeScript dans le HTML.

---

## 🎯 Property Binding - Lier des propriétés
```html
<img [src]="imageUrl" alt="Mon image">
<button [disabled]="isButtonDisabled">Cliquer</button>
<div [class]="cssClass">Contenu stylé</div>
```
**💡 À retenir :** Les crochets `[ ]` lient une propriété HTML à une variable TypeScript.

---

## ⚡ Event Binding - Gérer les événements
```html
<button (click)="increment()">+1</button>
<input (keyup)="onKeyUp($event)">
<form (submit)="onSubmit()">
```
**💡 À retenir :** Les parenthèses `( )` capturent les événements HTML et appellent des méthodes TypeScript.

---

## 🔄 Two-way Binding - Liaison bidirectionnelle
```html
<input [(ngModel)]="userName" placeholder="Votre nom">
<p>Bonjour {{ userName }} !</p>
```
**💡 À retenir :** `[(ngModel)]` combine property binding et event binding. Les modifications dans l'input se reflètent automatiquement dans la variable !

**⚠️ Important :** N'oublie pas d'importer `FormsModule` dans ton module pour utiliser `ngModel`.

---

## 🎯 Exemple Complet

**TypeScript (component.ts)**
```typescript
export class MyComponent {
  message = "Hello Angular !";
  imageUrl = "assets/logo.png";
  userName = "";
  counter = 0;
  isButtonDisabled = false;

  increment() {
    this.counter++;
  }
}
```

**HTML (component.html)**
```html
<h1>{{ message }}</h1>
<img [src]="imageUrl" alt="Logo">
<input [(ngModel)]="userName" placeholder="Ton nom">
<p>Salut {{ userName }} ! 👋</p>
<button (click)="increment()" [disabled]="isButtonDisabled">
  Compteur: {{ counter }}
</button>
```

---

## 🧠 Mémo Rapide
| Syntaxe | Usage | Exemple |
|---------|-------|---------|
| `{{ }}` | 📤 HTML ← TypeScript | `{{ title }}` |
| `[prop]` | 📤 HTML ← TypeScript | `[src]="url"` |
| `(event)` | 📥 HTML → TypeScript | `(click)="save()"` |
| `[(ngModel)]` | 🔄 HTML ↔ TypeScript | `[(ngModel)]="name"` |

**🚀 Astuce :** Ces 4 syntaxes couvrent 90% de tes besoins pour faire communiquer HTML et TypeScript !