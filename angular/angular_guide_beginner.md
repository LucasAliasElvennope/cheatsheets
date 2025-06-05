# Guide Angular pour Débutants
## Routing, Services et Structure Avancée

---

## 1. Routing et Navigation

Le routing dans Angular permet de naviguer entre différentes pages/vues de votre application sans recharger la page entière.

### Créer et configurer `app-routing.module.ts`

Le fichier de routing est le cœur de la navigation dans Angular.

**Étape 1 : Générer le module de routing**
```bash
ng generate module app-routing --flat --module=app
```

**Étape 2 : Structure du fichier `app-routing.module.ts`**
```typescript
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { AccueilComponent } from './accueil/accueil.component';
import { ProfilComponent } from './profil/profil.component';

// Définition des routes
const routes: Routes = [
  { path: '', component: AccueilComponent },           // Page d'accueil
  { path: 'profil', component: ProfilComponent },      // Page profil
  { path: '**', redirectTo: '' }                       // Route par défaut (404)
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

**Explication pour débutant :**
- `Routes` : tableau qui associe une URL à un composant
- `path: ''` : page d'accueil (URL vide)
- `path: '**'` : route "catch-all" pour les URLs non trouvées

### Définir les routes de base

**Exemple complet de routes :**
```typescript
const routes: Routes = [
  { path: '', component: AccueilComponent },
  { path: 'accueil', component: AccueilComponent },
  { path: 'produits', component: ProduitsComponent },
  { path: 'contact', component: ContactComponent },
  { path: 'profil/:id', component: ProfilComponent }, // Avec paramètre
  { path: '**', redirectTo: '' }
];
```

### Ajouter `<router-outlet>` dans `app.component.html`

C'est l'endroit où Angular affichera le contenu des différentes pages.

**Dans `app.component.html` :**
```html
<header>
  <nav>
    <a routerLink="/">Accueil</a>
    <a routerLink="/produits">Produits</a>
    <a routerLink="/contact">Contact</a>
  </nav>
</header>

<!-- C'est ici que le contenu des pages s'affiche -->
<router-outlet></router-outlet>

<footer>
  <p>Mon site Angular</p>
</footer>
```

### Naviguer avec `[routerLink]`

**Méthode simple :**
```html
<a routerLink="/accueil">Aller à l'accueil</a>
<a routerLink="/produits">Voir les produits</a>
```

**Méthode avec tableau (plus flexible) :**
```html
<a [routerLink]="['/profil', 123]">Voir profil #123</a>
<!-- Équivaut à /profil/123 -->
```

**Avec classes CSS actives :**
```html
<a routerLink="/accueil" routerLinkActive="active">Accueil</a>
```

### Ajouter une route avec paramètre (`:id`)

**Dans `app-routing.module.ts` :**
```typescript
const routes: Routes = [
  { path: 'produit/:id', component: ProduitDetailComponent },
  { path: 'utilisateur/:id/:nom', component: UtilisateurComponent }
];
```

**Utilisation :**
```html
<a [routerLink]="['/produit', 42]">Produit #42</a>
<!-- Génère l'URL : /produit/42 -->
```

### Récupérer un paramètre avec `ActivatedRoute`

**Dans le composant (`produit-detail.component.ts`) :**
```typescript
import { Component, OnInit } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'app-produit-detail',
  template: `
    <h2>Détail du produit #{{ produitId }}</h2>
    <p>Nom du produit : {{ nomProduit }}</p>
  `
})
export class ProduitDetailComponent implements OnInit {
  produitId: string = '';
  nomProduit: string = '';

  constructor(private route: ActivatedRoute) {}

  ngOnInit() {
    // Récupérer l'ID depuis l'URL
    this.produitId = this.route.snapshot.paramMap.get('id') || '';
    
    // Ou pour des paramètres qui changent dynamiquement :
    this.route.paramMap.subscribe(params => {
      this.produitId = params.get('id') || '';
      this.chargerProduit();
    });
  }

  chargerProduit() {
    // Logique pour charger le produit
    this.nomProduit = `Produit numéro ${this.produitId}`;
  }
}
```

---

## 2. Créer et utiliser un service Angular

Les services permettent de centraliser la logique métier et les données, les rendant réutilisables dans toute l'application.

### Générer un service avec `ng generate service`

**Commande :**
```bash
ng generate service services/produit
# ou plus court :
ng g s services/produit
```

Cela crée :
- `src/app/services/produit.service.ts`
- `src/app/services/produit.service.spec.ts` (tests)

### Comprendre le décorateur `@Injectable()`

**Structure d'un service (`produit.service.ts`) :**
```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'  // Le service est disponible dans toute l'app
})
export class ProduitService {
  private produits = [
    { id: 1, nom: 'Ordinateur', prix: 800 },
    { id: 2, nom: 'Souris', prix: 25 },
    { id: 3, nom: 'Clavier', prix: 50 }
  ];

  // Méthode pour obtenir tous les produits
  getProduits() {
    return this.produits;
  }

  // Méthode pour obtenir un produit par ID
  getProduitById(id: number) {
    return this.produits.find(p => p.id === id);
  }

  // Méthode pour ajouter un produit
  ajouterProduit(produit: any) {
    const nouveauId = Math.max(...this.produits.map(p => p.id)) + 1;
    this.produits.push({ ...produit, id: nouveauId });
  }
}
```

**Explication pour débutant :**
- `@Injectable()` : dit à Angular que cette classe peut être injectée dans d'autres classes
- `providedIn: 'root'` : crée une instance unique du service pour toute l'application

### Injecter un service dans un composant avec le constructeur

**Dans un composant (`produits.component.ts`) :**
```typescript
import { Component, OnInit } from '@angular/core';
import { ProduitService } from '../services/produit.service';

@Component({
  selector: 'app-produits',
  template: `
    <h2>Liste des produits</h2>
    <div *ngFor="let produit of produits">
      <h3>{{ produit.nom }}</h3>
      <p>Prix : {{ produit.prix }}€</p>
    </div>
  `
})
export class ProduitsComponent implements OnInit {
  produits: any[] = [];

  // Injection du service dans le constructeur
  constructor(private produitService: ProduitService) {}

  ngOnInit() {
    // Utilisation du service
    this.produits = this.produitService.getProduits();
  }
}
```

### Centraliser des données (tableau, messages, etc.)

**Exemple d'un service de messages :**
```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class MessageService {
  private messages: string[] = [];

  ajouter(message: string) {
    this.messages.push(message);
  }

  effacer() {
    this.messages = [];
  }

  getMessages() {
    return this.messages;
  }
}
```

---

## 3. Injection de dépendances

L'injection de dépendances est un pattern où Angular fournit automatiquement les instances des services dont vos composants ont besoin.

### Comprendre le système d'injection Angular

**Principe simple :**
1. Vous déclarez dans le constructeur ce dont vous avez besoin
2. Angular se charge de créer et fournir l'instance

**Exemple :**
```typescript
export class MonComposant {
  constructor(
    private produitService: ProduitService,
    private messageService: MessageService
  ) {
    // Angular injecte automatiquement les services
  }
}
```

### Utiliser `providedIn: 'root'` pour un singleton global

```typescript
@Injectable({
  providedIn: 'root'  // UNE SEULE instance pour toute l'app
})
export class UtilisateurService {
  private utilisateurConnecte = { nom: 'Jean', email: 'jean@email.com' };

  getUtilisateur() {
    return this.utilisateurConnecte;
  }
}
```

**Avantage :** Même données partagées partout dans l'application.

### Ajouter un service à un module spécifique si nécessaire

**Si vous voulez limiter un service à un module :**
```typescript
// Dans le module
@NgModule({
  providers: [MonServiceSpecifique]  // Disponible seulement dans ce module
})
export class MonModule { }
```

---

## 4. Structure avancée

### Créer un composant enfant

**Générer un composant enfant :**
```bash
ng generate component components/carte-produit
```

**Composant enfant (`carte-produit.component.ts`) :**
```typescript
import { Component, Input, Output, EventEmitter } from '@angular/core';

@Component({
  selector: 'app-carte-produit',
  template: `
    <div class="carte">
      <h3>{{ produit.nom }}</h3>
      <p>Prix : {{ produit.prix }}€</p>
      <button (click)="acheter()">Acheter</button>
    </div>
  `,
  styles: [`
    .carte {
      border: 1px solid #ccc;
      padding: 10px;
      margin: 10px;
      border-radius: 5px;
    }
  `]
})
export class CarteProduitComponent {
  @Input() produit: any = {};  // Données reçues du parent
  @Output() achat = new EventEmitter<any>();  // Événement envoyé au parent

  acheter() {
    this.achat.emit(this.produit);  // Envoie l'événement au parent
  }
}
```

### Transmettre des données avec `@Input`

**Composant parent (`produits.component.ts`) :**
```typescript
@Component({
  selector: 'app-produits',
  template: `
    <h2>Nos produits</h2>
    <!-- Passage de données au composant enfant -->
    <app-carte-produit 
      *ngFor="let produit of produits"
      [produit]="produit"
      (achat)="onAchat($event)">
    </app-carte-produit>
  `
})
export class ProduitsComponent {
  produits = [
    { id: 1, nom: 'Ordinateur', prix: 800 },
    { id: 2, nom: 'Souris', prix: 25 }
  ];

  onAchat(produitAchete: any) {
    console.log('Produit acheté :', produitAchete);
    // Logique d'achat
  }
}
```

### Réagir à des événements avec `@Output` + `EventEmitter`

**Composant enfant plus détaillé :**
```typescript
import { Component, Input, Output, EventEmitter } from '@angular/core';

@Component({
  selector: 'app-formulaire-contact',
  template: `
    <form (ngSubmit)="envoyer()">
      <input [(ngModel)]="nom" placeholder="Votre nom" required>
      <input [(ngModel)]="email" placeholder="Votre email" required>
      <button type="submit">Envoyer</button>
    </form>
  `
})
export class FormulaireContactComponent {
  @Input() titre: string = '';
  @Output() messageEnvoye = new EventEmitter<{nom: string, email: string}>();
  
  nom: string = '';
  email: string = '';

  envoyer() {
    if (this.nom && this.email) {
      // Émet l'événement vers le parent
      this.messageEnvoye.emit({
        nom: this.nom,
        email: this.email
      });
      
      // Remet à zéro le formulaire
      this.nom = '';
      this.email = '';
    }
  }
}
```

**Utilisation dans le parent :**
```typescript
@Component({
  template: `
    <app-formulaire-contact 
      titre="Contactez-nous"
      (messageEnvoye)="traiterMessage($event)">
    </app-formulaire-contact>
  `
})
export class ContactComponent {
  traiterMessage(donnees: {nom: string, email: string}) {
    console.log('Message reçu de :', donnees.nom);
    console.log('Email :', donnees.email);
    // Traitement du message
  }
}
```

---

## Résumé pour débutant

### Concepts clés à retenir :

1. **Routing** : Permet de naviguer entre les pages
   - `routerLink` pour créer des liens
   - `ActivatedRoute` pour récupérer les paramètres d'URL

2. **Services** : Centralisent la logique et les données
   - Générés avec `ng g s`
   - Injectés dans les composants via le constructeur

3. **Communication parent-enfant** :
   - `@Input` : parent → enfant (données)
   - `@Output` : enfant → parent (événements)

4. **Injection de dépendances** : Angular fournit automatiquement ce dont vous avez besoin

### Ordre d'apprentissage recommandé :
1. Créer des composants de base
2. Apprendre le routing simple
3. Créer votre premier service
4. Maîtriser @Input et @Output
5. Approfondir le routing avec paramètres

N'hésitez pas à pratiquer chaque concept un par un avant de passer au suivant !