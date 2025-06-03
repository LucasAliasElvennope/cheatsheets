# 🧩 Cheat-sheet : Décorateur @Component (Angular)

## ✅ Rôle principal :
Transforme une **classe TypeScript** en **composant Angular** avec des **métadonnées** qui indiquent :
- Où l’afficher (`selector`)
- Quel template utiliser (`templateUrl` ou `template`)
- Quel style appliquer (`styleUrls` ou `styles`)

---

## 🔧 Structure de base :

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-nom-du-composant',
  templateUrl: './nom-du-composant.html',
  styleUrls: ['./nom-du-composant.css']
})
export class NomDuComposant {
  // Logique du composant ici
}
```
---

### 🧠 Propriétés du décorateur :

|Propriété	|Description|
|---|---|
|selector	|🔹 Nom de la balise HTML personnalisée|
|templateUrl	|🔹 Chemin vers le fichier HTML externe|
|template	|🔹 (Optionnel) HTML écrit directement dans le TS|
|styleUrls|	🔹 Liste des fichiers CSS externes|
|styles	|🔹 (Optionnel) CSS écrit directement dans le TS|

***EXEMPLE :***

```ts
@Component({
  selector: 'app-nom-du-composant',
  templateUrl: './nom-du-composant.html',
  styleUrls: ['./nom-du-composant.css']
})
```

### 📌 Rappels :

- Chaque composant Angular doit avoir un @Component.

- Un module (via @NgModule) doit déclarer le composant pour qu’il soit utilisé.

- Angular utilise le selector pour insérer le composant dans le DOM.