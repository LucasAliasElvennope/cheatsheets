# Angular Project Structure Cheat Sheet

---

## I. Racine du Projet (`mon-app/` ou `<votre-nom-de-projet>/`)

C'est le dossier principal de votre application, contenant la configuration globale.

* **`angular.json`**
    * **Rôle :** Fichier de configuration de l'**Angular CLI**.
    * **Contient :** Structure de l'espace de travail, projets, configurations de `build`, styles globaux, scripts.
    * **Utilité :** Indique à Angular comment construire, servir et tester votre app.

* **`package.json`**
    * **Rôle :** Fichier standard de **Node.js/npm**.
    * **Contient :** Liste de toutes les **dépendances** (bibliothèques tierces) du projet et les **scripts** npm (`start`, `build`, `test`, etc.).
    * **Voir aussi :** `node_modules/` (où sont installées les dépendances, généralement ignoré par Git).

* **`tsconfig.json` (et apparentés ex: `tsconfig.app.json`)**
    * **Rôle :** Fichiers de configuration de **TypeScript**.
    * **Contient :** Règles de compilation TypeScript (version cible de JS, chemins de module, etc.).
    * **Utilité :** Indique à TypeScript comment interpréter et compiler votre code.

* **`karma.conf.js` / `protractor.conf.js` (ou équivalents)**
    * **Rôle :** Configurations pour les outils de **test** (Karma pour les tests unitaires, Protractor/Cypress/Playwright pour les tests E2E).

---

## II. Répertoire Source (`src/`)

Le cœur de votre application. Tout le code source de l'application est ici.

* **`index.html`**
    * **Rôle :** Le **point d'entrée unique** de l'application web.
    * **Contient :** La balise `<app-root></app-root>` (ou le sélecteur de votre composant racine) où l'application Angular sera injectée.
    * **Important :** C'est le seul fichier HTML complet chargé par le navigateur.

* **`main.ts`**
    * **Rôle :** Le **point d'entrée TypeScript** de l'application.
    * **Contient :** Le code qui initialise l'environnement Angular et démarre (`bootstrap`) le composant racine (`AppComponent`).

* **`styles.scss` (ou `styles.css`)**
    * **Rôle :** Contient les **styles CSS globaux** de l'application.
    * **Utilité :** Applique des styles qui affectent tous les composants, sauf s'ils sont spécifiques et écrasés.

* **`polyfills.ts`**
    * **Rôle :** Ajoute des fonctionnalités **compatibilité** (polyfills) pour les navigateurs plus anciens, afin qu'ils puissent exécuter le code moderne.

* **`assets/`**
    * **Rôle :** Stocke les **ressources statiques**.
    * **Contient :** Images, icônes, polices, fichiers JSON statiques.
    * **Utilité :** Le contenu de ce dossier est copié tel quel dans le dossier de sortie (`dist/`) lors du `build`.

* **`environments/`**
    * **Rôle :** Contient des fichiers de **configuration spécifiques à l'environnement**.
    * **Contient :** `environment.ts` (développement) et `environment.prod.ts` (production).
    * **Utilité :** Permet d'avoir des variables différentes (ex: URL d'API) selon l'environnement de compilation.

---

## III. Répertoire de l'Application (`src/app/`)

C'est là que réside la majeure partie de votre code spécifique à l'application.

* **`app.component.ts` / `.html` / `.scss`**
    * **Rôle :** Le **composant racine** de votre application.
    * **Utilité :** Agit souvent comme le "shell" global, contenant des éléments communs (en-tête, pied de page) et le `<router-outlet>`.

* **Sous-répertoires de composants (ex: `header/`, `user/`, `products/`)**
    * **Rôle :** Organisation des **composants spécifiques** à des fonctionnalités.
    * **Contient :** Généralement tous les fichiers d'un même composant (`.component.ts`, `.html`, `.scss`, `.spec.ts`).
    * **Utilité :** Facilite la gestion et la réutilisabilité des composants par fonctionnalité.

* **Fichiers de service (ex: `logging.service.ts`, `auth.service.ts`)**
    * **Rôle :** Contiennent la **logique métier** et les fonctionnalités partagées.
    * **Utilité :** Souvent placés à la racine de `src/app/` s'ils sont globaux, ou dans des sous-dossiers pertinents (ex: `src/app/services/`).

* **Fichiers de routage (ex: `app.routes.ts` ou `app-routing.module.ts`)**
    * **Rôle :** Définit les **routes** de votre application.
    * **Utilité :** Mappe les URL aux composants correspondants pour la navigation.

---

J'espère que cette feuille de triche vous aidera à mieux naviguer dans la structure de vos projets Angular ! Est-ce qu'il y a d'autres aspects de la structure de projet que vous aimeriez explorer ?