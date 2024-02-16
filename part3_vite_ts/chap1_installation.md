# Cours sur Vite - Un outil de build rapide pour les applications web

## Introduction à Vite

> [!NOTE]
> Vite est un outil de build et de développement rapide pour les applications web. Conçu par Evan You, le créateur de Vue.js, Vite offre des temps de développement rapides en tirant parti des fonctionnalités des modules ECMAScript (ES modules).

## Installation de Vite

:rocket: Pour créer un nouveau projet Vite, vous pouvez utiliser la commande suivante :

```bash
npm init vite@latest app-dragon
```

Vous pouvez également utiliser `yarn` à la place de `npm` si vous le préférez, mais dans la suite du cours on utilisera npm.

## Structure d'un projet Vite

:heart: Le projet Vite généré aura une structure de base qui ressemble à ceci :

```
mon-projet/
|-- node_modules/
|-- public/
|-- src/
|   |-- components/
|   |-- App.vue
|   |-- main.js
|-- .gitignore
|-- package.json
|-- README.md
```

- Le dossier `src` contient le code source de votre application.
- Le fichier `App.vue` est le composant principal de l'application.
- Le fichier `main.js` est le point d'entrée de l'application.

## Développement avec Vite

Pour lancer le serveur de développement, utilisez la commande suivante :

```bash
npm run dev
```

Cela démarrera un serveur de développement sur `http://localhost:3000` par défaut.

## Gestion des Dépendances

Vite utilise le gestionnaire de paquets `esbuild` pour une gestion efficace des dépendances. Vous pouvez installer des dépendances avec `npm install` ou `yarn add`.

## Configuration de Vite

Vite ne nécessite généralement pas de configuration, mais si vous en avez besoin, vous pouvez créer un fichier `vite.config.js` à la racine de votre projet.

## Production avec Vite

Pour construire votre application pour la production, utilisez la commande suivante :

```bash
npm run build
```

Cela générera un dossier `dist` avec les fichiers optimisés prêts à être déployés, si vous développez en TS les builds seront la traduction de TS en JS.

