# Exemple d'application avec TypeScript

### Qu'est-ce que TypeScript ?
### Typage statique

### Installation et configuration

1. Utilisez la version de Node.js LTS, voir sur le site Node.js
1. Initialisez le projet (le cours) : lessons
   - TypeScript est installé en tant que devDependencies
1. Arborescence pour notre cours

:rocket:

## Qu'est-ce que TypeScript ?

TypeScript est un langage de programmation open source développé par Microsoft. 

Il s'agit d'un sur-ensemble de JavaScript, ce qui signifie que tout code JavaScript valide est également du code TypeScript. 

Cependant, TypeScript offre des fonctionnalités supplémentaires qui ajoutent de la puissance et de la flexibilité au développement d'application.

>[!NOTE]
>L'une des caractéristiques principales de TypeScript est le support du typage statique. 

Contrairement à JavaScript, où les types de variables sont déterminés à l'exécution, TypeScript permet de spécifier le type des variables lors de la phase de développement. Cela permet de détecter et de corriger les erreurs potentielles dans le processus de développement.

## Typage statique

Le typage statique permet de définir explicitement le type des variables, paramètres de fonction, et valeurs de retour. Cela aide à détecter les erreurs de typage dès le stade de la compilation, offrant ainsi une plus grande sécurité et robustesse dans le code.

```ts
function add(a: number, b: number): number {
  return a + b;
}

const result: number = add(3, 5);
```

### Mise en pratique

1. :rocket: Si vous souhaitez ajouter des dépendances TypeScript, vous pouvez les installer avec :

```bash
npm install --save-dev typescript @types/node 
```

Assurez-vous d'ajuster les types en fonction du framework ou de la bibliothèque que vous utilisez dans votre projet.

Avec ces étapes, votre projet Vite sera configuré avec TypeScript prêt à être utilisé. Vous pouvez ajouter des fichiers TypeScript dans le dossier `src` et bénéficier de la typage statique fourni par TypeScript.

### Exercice Dragon

Affichez les dragons dans votre projet sur la page principale.