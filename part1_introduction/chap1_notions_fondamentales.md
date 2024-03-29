# JS rappel des fondamentaux

## Sommaire

- [JS rappel des fondamentaux](#js-rappel-des-fondamentaux)
  - [Sommaire](#sommaire)
  - [Introduction \& histoire de JS ](#introduction--histoire-de-js-)
  - [Notion de type en JS ](#notion-de-type-en-js-)
  - [Les différents types en JS ](#les-différents-types-en-js-)
    - [Types primitifs ](#types-primitifs-)
    - [Les types Objects ](#les-types-objects-)
  - [Ce qui est considéré comme faux en JS ](#ce-qui-est-considéré-comme-faux-en-js-)
  - [Evaluations courcircuit  ](#evaluations-courcircuit--)
  - [Les chaînes de caractères Interpolation  ](#les-chaînes-de-caractères-interpolation--)
  - [Portée (ou scope en Anglais) des variables en JS ](#portée-ou-scope-en-anglais-des-variables-en-js-)
    - [Remonter des scopes ](#remonter-des-scopes-)
    - [Exercice scope calcul (sans coder)  ](#exercice-scope-calcul-sans-coder--)
    - [Exercice TDZ (temporal dead zone) (sans coder) ](#exercice-tdz-temporal-dead-zone-sans-coder-)
    - [Exercice for let (sans coder) ](#exercice-for-let-sans-coder-)
  - [Déclaration d'une constante ](#déclaration-dune-constante-)
    - [Exercice const \& for ](#exercice-const--for-)
  - [var définition obsolète ! ](#var-définition-obsolète--)
  - [Introduction à la notion de fonction ](#introduction-à-la-notion-de-fonction-)
    - [Paramètres facultatif ](#paramètres-facultatif-)
      - [Exercice ttc ](#exercice-ttc-)
    - [Syntaxe par décomposition ](#syntaxe-par-décomposition-)
      - [Exercice fonction ttc spread operator ](#exercice-fonction-ttc-spread-operator-)
    - [littéral pour définir des paramètres ](#littéral-pour-définir-des-paramètres-)
    - [Exercice somme caractères](#exercice-somme-caractères)
    - [this dans le contexte de l'appel d'une fonction sur un objet ](#this-dans-le-contexte-de-lappel-dune-fonction-sur-un-objet-)
  - [Exercice sur les objets](#exercice-sur-les-objets)
    - [Partie 1](#partie-1)
    - [Partie 2](#partie-2)
    - [Déclaration de fonction ](#déclaration-de-fonction-)
      - [Exercice function \& expression ](#exercice-function--expression-)
      - [Exercice déclaration d'une fonction ](#exercice-déclaration-dune-fonction-)
    - [L'objet arguments et paramètres d'une fonction ](#lobjet-arguments-et-paramètres-dune-fonction-)
    - [Les fonctions fléchées ](#les-fonctions-fléchées-)
    - [Fonction constructeur  ](#fonction-constructeur--)
    - [Exercice de synthèse corrigé un effet de bord ](#exercice-de-synthèse-corrigé-un-effet-de-bord-)
    - [Introduction à la notion de prototype pour une fonction  ](#introduction-à-la-notion-de-prototype-pour-une-fonction--)
      - [(Application) Ajouter une propriété sur un constructeur ](#application-ajouter-une-propriété-sur-un-constructeur-)
      - [Exercice prototype average pour la fonction User ](#exercice-prototype-average-pour-la-fonction-user-)
  - [Quelques fonctions JS utiles pour le traitement des données  ](#quelques-fonctions-js-utiles-pour-le-traitement-des-données--)
    - [La fonction JS map ](#la-fonction-js-map-)
      - [Exercice puissance 3 ](#exercice-puissance-3-)
      - [Exercice max ](#exercice-max-)
      - [Exercice reduce sum impair ](#exercice-reduce-sum-impair-)
      - [Exercice fonction map sur un littéral ](#exercice-fonction-map-sur-un-littéral-)
  - [Affectation par décomposition ](#affectation-par-décomposition-)
    - [Exercice permutations ](#exercice-permutations-)


## Introduction & histoire de JS <a class="anchor" id="chapter1"></a>

JS première version 1995, auteur Brendan Eich.

Rappelons que JS est un langage interprété dont le typage est faible. Mais attention, cela ne veut pas dire que JS ne définit pas un type à ses variables.

:pill: Un typage faible permet les convertions de type implicite et explicite :

```js
// conversion implicite 
let foo = 1 + "2";

// Conversions explicites
let str = "123";    // chaine est de type string
let number = Number(str); // 
```

Et JS a un typage dynamique, le type est déterminé à l'exécution :

```js
// Le type de a sera défini à l'exécution de cette ligne
let a = 1;
```

> [!NOTE] 
> Un langage interprété utilise le code source pour le compiler puis l'exécuter, il n'y a pas de création d'exécutable définitif. Pour chaque exécution, JS repartira du code source.

Le moteur JS de compilation peut taguer du code qui se répète et créer, pour ces parties uniquement, un exécutable "définitif".

JS est un langage de script orienté objet.

JS suit la norme **ECMAScript**, standard que suivent certains langages de script comme Javascript. Cette norme évolue en permanence. Les principaux navigateurs Web mettent à jour leur moteur d'exécution pour suivre les évolutions de ce langage.

Une version majeure d'ECMAScript est celle qui a été définie en 2015 : ES2015 que l'on appelle ES6. Le nom de la version étant déterminé par la dernière version du standard en cours donc ES6 pour 2015. Aujourd'hui la dernière version officielle est EMACScript 2020.

## Notion de type en JS <a class="anchor" id="chapter2"></a>

Bien que JS soit un langage faiblement typé, JS type toutes ses variables.

Le type d'une variable en JS est déterminé lorsqu'on la définit et qu'on lui assigne une valeur particulière. Ce dernier peut changer si on ré-assigne à la variable une valeur d'un autre type.

```js
let n = 10;
console.log(typeof n); // number

// ré-assignation
n = "Hello";

console.log(typeof n); // string
```

Dans l'exemple ci-dessus le type de la variable **n** a changé; il est passé du type number au type string (par ré-assignation).

Notons que lorsque vous définissez une variable sans lui affecter une valeur particulière, celle-ci est de type "undefined" :

```js
let username;
console.log(typeof username); // undefined
```

## Les différents types en JS <a class="anchor" id="chapter3"></a>

On distingue les types suivants en Javascript. Attention, tous les types primitifs définissent des valeurs non modifiables (immuables).

### Types primitifs <a class="anchor" id="section31"></a>

- boolean

```js

// On ne peut pas modifier un "true" ...
let flag = true;
```

- null

```js
// On ne peut pas modifier un "null" ...
let flag = null;
```

- undefined

- number

- bigInt (big integer)

Il faut ajouter l'opérateur **n** pour définir des BigInt.

```js
const x = 2n ** 100n;
console.log(x);
// 1267650600228229401496703205376n
```

- string

```js
let message = "Hello World";
```

- symbole (type introduit à partir de la norme ES6, que nous n'aborderons pas dans ce cours).


------

### Les types Objects <a class="anchor" id="section32"></a>

Ils sont mutables, on peut modifier la valeur d'un objet. Un objet est une valeur conservée en mémoire à l'aide d'une référence unique.

Dans la liste des objets vous avez :

- Les objets classiques : les classes et les fonctions.

```js
class Model {

  get() {
    return "table";
  }
}

// Création d'un instance (objet)
const myModel = new Model();

function modelFunc(n) {
  let name = n;

  return name;
}
```

- Les objets natifs comme les dates

```js
const now = new Date();
```

- Les collections comme les tableaux, Map, Set, ...

Les déclarations suivantes pour un tableau sont identiques :

```js
let notes = [1, 2, 3];
let newNotes = new Array(1, 2, 4);
```

Un Map est une simple collection de clés/valeurs. 

```js
// création d'un Map
const store = new Map();

store.set("A1", 10.6);
store.set("A2", 8.9);

console.log(store);
// {"A1" => 10.6, "A2" => 8.9}

const ensemble = new Set([1, 2, 3, 4, 5, 5]);
console.log(ensemble);
// [1, 2, 3, 4, 5] il n'y a pas de doublon
```

- Les JSON Javascript Object Notation

## Ce qui est considéré comme faux en JS <a class="anchor" id="section33"></a>

0, NaN, undefined, false, "", '', \`\`, null

*Notez que tout le reste n'est pas considérer comme faux. Tout ce qui a une valeur est donc considérée comme vraie.*

## Evaluations courcircuit  <a class="anchor" id="section34"></a>

- Dans le cas où user n'est pas défini avec le connecteur ET 

```js
false && user 
```
- Avec un OU

```js
true || user
```

## Les chaînes de caractères Interpolation  <a class="anchor" id="section35"></a>

Vous pouvez écrire des chaînes de caractères sur plusieurs lignes et insérer des expressions JS qui seront évaluées à l'aide de backquotes (accent grave).

Exemple

```js
let a = 51;
let b = 90;
console.log("Somme " + (a + b) + " et\n multiplication " + a * b + ".");
```

Avec les backquotes on aura une expression plus facile à écrire :

```js
let a = 51;
let b = 90;
console.log(`Somme : ${a + b} et \n multiplication : ${a * b}.`);
```

Exemple avec une expression JS :

```js
let isLoading = true;
const message = `Data is ${isLoading ? 'loading...' : 'done!'}`;
```

Remarque sur la syntaxe ternaire, pour écrire une condition sur une ligne :

```js

console.log( true ? 'yes' : 'no'; ); // yes
console.log( false ? 'yes' : 'no'; ); // no

```

Les ternaires sont également très pratiques pour assigner des valeurs avec une condition :

```js
logged = true ? 'yes' : 'no'; ; // yes

logeed =  false ? 'yes' : 'no'; ; // no

```

Vous pouvez enchaîner les ternaires mais, attention à la lisibilité.

```js
logged = true ? ( true ? 'toujours yes' : 'no' )  : 'no'; ; // toujours yes
```

## Portée (ou scope en Anglais) des variables en JS <a class="anchor" id="chapter4"></a>

Définition let :
**La variable définie avec let a une portée scopée au niveau du bloc dans lequel elle a été déclarée.**

*Remarque importante : lorsque vous définissez une variable à l'intérieur d'une fonction elle est scopée (portée) dans la fonction elle-même; elle n'a pas d'effet de bord avec le reste du script.*

```js

function foo() {
  let a = 10;
  console.log(a); // affiche 10
}

foo();

// ReferenceError
console.log(a);
```

Si vous définissez une variable **de même nom** à l'extérieur de la fonction, alors elle n'aura pas d'effet sur la variable définie à l'intérieur de la fonction foo :

```js
let a = 11;

function foo() {
  let a = 10;
  console.log(a); 
}

// affiche 10
foo();

// affiche 11
console.log(a);
```

### Remonter des scopes <a class="anchor" id="section41"></a>

JS cherche la définition de ses variables dans le scope courant et sinon il remonte les scopes. Si la variable n'est définie dans aucun des scopes, alors une erreur **ReferenceError** est levée.

```js
// bloc courant pour b
let b = 11;

function baz() {
  // bloc courant pour c
  let c = 9;

  // JS ne trouve pas b dans le bloc courant => il remonte les scopes
  console.log(b, c);
}

// affiche 11 9
baz();

```

Un autre exemple :

```js
// bloc courant
let b = 11;

function baz() {
  console.log(b);

  function foo() {
    console.log("Valeur du symbole b : ", b);
  }

  foo();
}

// affiche 11
baz();
```

### Exercice scope calcul (sans coder)  <a class="anchor" id="section42"></a>

Est ce que le code qui suit vous semble correcte ? Répondre sans exécuter le code. Si ce dernier n'est pas valide modifiez-le afin qu'il puisse s'exécuter correctement.

```js

let a = 1;

function calcul() {
  let a = 2 + a;

  console.log(a, "calcul");

  function sub_calcul() {
    let b = a + 1;

    console.log(b, "sub_calcul");
  }

  sub_calcul();
}

calcul();

```

### Exercice TDZ (temporal dead zone) (sans coder) <a class="anchor" id="section43"></a>

Est ce que le code qui suit vous semble correcte ? Répondez sans exécuter le code.

```js
function tdz() {
  console.log(tdz_val);

  let tdz_val = "Temporal Dead Zone";
}

tdz();
```

### Exercice for let (sans coder) <a class="anchor" id="section44"></a>

Est ce que le code qui suit vous semble correcte ? Répondez sans exécuter le code.

```js
let i = 100;

for (let i = 0; i < 10; i++) {
  console.log(i);
}

console.log(i);
```

Est ce que le code qui suit vous semble correcte ? Répondez sans exécuter le code.

Si ce code est valide qu'affichera-t-il ?

```js
for (let j = 0; j < 10; j++) {}
console.log(j);
```

## Déclaration d'une constante <a class="anchor" id="chapter5"></a>

Définition :
**La variable définie avec const a une portée scopée au niveau du bloc dans lequel elle a été déclarée.**

Le mot réservé du langage JS **const** permet de définir une constante à assignation unique. Notez que vous êtes obligé de lui donner une valeur lors de sa définition. Une constante ne peut être re-définie.

```js
const API_KEY = "ABf#123@";
console.log(API_KEY);
```

Une constante peut contenir tous types de variable. Dans le cas d'un objet comme un tableau par exemple, les valeurs du tableau sont modifiables. En effet, une constante bloque la ré-assignation de la variable, mais ne rend pas l'objet non-modifiable.

```js

const STUDENTS = ["Alan", "Bernard", "Jean"];

STUDENTS.push("Sophie");

console.log(STUDENTS);
//["Alan", "Bernard", "Jean", "Sophie"]

STUDENTS.pop();

console.log(STUDENTS);
// ["Alan", "Bernard", "Jean"]

```

Par contre ce qui suit est impossible, l'erreur suivante sera levée :
**TypeError: Assignment to constant variable.**

```js
let newStudents = ["Alice"];
// re-assignation impossible
STUDENTS = newStudents;
```

### Exercice const & for <a class="anchor" id="section51"></a>

1. Pouvez-vous utiliser à votre avis le mot réservé const dans la boucle suivante ?

```js
for (const j = 0; j < 10; j++) {}
```

2. Utilisez la syntaxe de boucle for of et const sur l'itérable STUDENTS et affichez (console.log) ses valeurs :

```js
const STUDENTS = ["Alan", "Bernard", "Jean"];
```


## var définition obsolète ! <a class="anchor" id="chapter6"></a>

**Ce mot clé pour définir une variable ne doit plus être utilisé, utilisez let à la place.**

Il permet de définir une variable globale ou locale à une fonction sans distinction de bloc :

```js
function foo() {
  var x = 10; // portée fonction pas bloc comme let
  if (true) {
    var x = 2;  // c'est la même variable !
    console.log(x);  // 2
  }
  console.log(x);  // 2
}
foo(); // 2 2
```

Par comparaison avec le mot clé let :

```js
function bar() {
  let x = 10; // portée fonction pas bloc comme let
  if (true) {
    let x = 2;  // c'est la même variable !
    console.log(x);  // 2
  }
  console.log(x);  // 10
}
bar(); //  2 10
```

## Introduction à la notion de fonction <a class="anchor" id="chapter7"></a>

Une fonction en JS est un objet.

### Paramètres facultatif <a class="anchor" id="section71"></a>

```js
function add(a, sup = 1) {
  return a + sup;
}

add(10); // affiche 11

add(10, 0); // affiche 10

```

#### Exercice ttc <a class="anchor" id="section711"></a>

1. Créez une fonction qui permet de calculer un prix TTC connaissant un prix HT. Donnez une valeur de 20% par défaut pour la TVA.

2. Vérifiez que le type des variables passées en paramètre ne posent pas de problème. Utilisez **parseFloat** pour la vérification des types. Affichez les résultats avec au plus 2 chiffres après la virgule. 

```js

// 1.
ttc(100, 0.2); // 120
ttc(100.50, 0.2); // 144.72

// 2.
// Gestion du type
ttc("hello", 0.2); // Erreur de type
ttc(100.50, "hello"); // Erreur de type
ttc("100", ".3"); // 130
```

### Syntaxe par décomposition <a class="anchor" id="section72"></a>

Si vous avez une fonction avec de nombreux paramètres ou des paramètres variables, utilisez le spread operator pour passer les valeurs à la fonction :

```js
function sum(x, y, z) {
  return x + y + z;
}

let numbers = [1, 2, 3];

sum(...numbers); // sum(1, 2, 3) unpacking
```

#### Exercice fonction ttc spread operator <a class="anchor" id="section721"></a>

Ecrivez une fonction **sumTTC** qui prend 3 nombres arbitraires de prix HT et retourne la somme de ces prix TTC. La TVA est  un paramètre facultatif (20%).
Vérifiez que le type des variables passées en paramètre ne posent pas de problème, utilisez **parseFloat**. Affichez les résultats avec au plus 2 chiffres après la virgule.

Les prix HT seront donnés dans un tableau :

```js
const pricesHT = [100, 200, 55];

console.log(sumTTC(...priceHT));
console.log(sumTTC(...priceHT, .3));

// vérifiez le type des variables
const badPriceHT = [100.50, "hello", 55.7];
console.log(sumTTC(...badPriceHT, .3));
```

### littéral pour définir des paramètres <a class="anchor" id="section73"></a>

Vous pouvez utiliser la syntaxe suivante pour définir les paramètres d'une fonction. Dans ce cas vous n'avez pas à vous soucier de l'ordre des paramètres passé à la fonction.

```js
function baz({ a, b }){ 
  console.log(a, b ) 
}

baz({ a: 1, b : 2}); // 1 2
baz({ b: 2, a : 1}); // 1 2

```

### Exercice somme caractères

Soit la chaine de caractères suivantes, créez une fonction qui permet de faire la somme des a dans la chaine de caractères suivantes :

```js
const message = "aaasldkqldqaaaadkkdjfkdfjaaaa" ;
```

### this dans le contexte de l'appel d'une fonction sur un objet <a class="anchor" id="section74"></a>

Le this d'un objet est déterminé par la manière dont vous allez appeler l'objet "contexte".

L'objet sur lequel vous **appelez** la fonction détermine le this :

**objet.my_function()**

```js
'use strict';

const o1 = {
    f1 : function(){

      return this;
    }
}

console.log(o1.f1()) ; // this de o1

const o2 = {
    f2 : o1.f1
}

console.log(o2.f2()) ; // this de o2

const o3 = o1.f1;

console.log(o3()) ; // undefined car on n'appelle la fonction f1 explicitement
```

De même, faites attention dans les fonctions de callback. Dans l'exemple qui suit setTimeout fera appel à la fonction sans reprendre le context de l'objet lui-même, this sera, en mode strict, undefined :

```js
'use strict';

setTimeout(o1.f1, 1000); // ici setTimeout appel la fonction f1.
```

Pour corriger ce problème il faut écrire :

```js
setTimeout(() => o1.f1() , 1000); // ici setTimeout appel la fonction f1.
```

Bien sûr, je comprends maintenant. Voici le texte corrigé :

Voici le texte corrigé avec quelques ajustements :

## Exercice sur les objets

### Partie 1 

1. Créez un objet permettant de calculer la somme TTC de produits.
1. Définissez une méthode qui permet de spécifier une précision pour les valeurs retournées par l'objet.

### Partie 2 

1. Créez un objet permettant de compter tous les caractères d'une chaîne.
1. Ajoutez une méthode qui recherche si un caractère est présent dans la chaîne.
1. Intégrez une méthode qui recherche une chaîne de caractères dans une autre chaîne.
1. Intégrez une méthode qui supprime des caractères.

Envisagez maintenant l'objet de la partie 2 à être appelé dans un autre objet.

1. L'objet à implémenter doit prendre un texte et retourner un tableau de nombres qui donne uniquement les occurrences de chaque lettre.

### Déclaration de fonction <a class="anchor" id="section75"></a>

En JS vous avez des fonctions déclarées et des expressions de fonction.

- fonction déclarée :

```js
function foo(){

}
```

- Expression de fonction

```js
setTimeout( function (){

})
```

#### Exercice function & expression <a class="anchor" id="section751"></a>

Nommez les types de fonction ci-dessous :

```js
const myFunc = function(){

  function bar(){
    // ...
  }
}
```

Les fonctions déclarées sont définies dès le début du script ou de la fonction qui la contient.

Les expressions de fonction sont définies après leur évaluation.

#### Exercice déclaration d'une fonction <a class="anchor" id="section752"></a>

*Sans exécuter le code.* 

1. Le code suivant est-il valide ?

```js
bar();

function bar(){
  console.log("bar");
}
```

2. Le code suivant est-il valide ?

```js
myFunc(); 

const myFunc = function(){
    console.log("Expression");
}
```

### L'objet arguments et paramètres d'une fonction <a class="anchor" id="section76"></a>

Vous n'êtes pas obligé de renseigner le nombre d'argument(s) d'une fonction en JS. La fonction possède en interne une propriété **arguments** qui récupère les paramètres de la fonction, attention arguments n'est pas un tableau :

```js
function sum(){
  let total = 0;
  for(let i =0; i < arguments.length; ++i ) total += arguments[i];

  return total;
}

console.log(sum(1,2,3,4, 5, 6));
```

L'objet arguments peut-être converti en tableau à l'aide de la méthode from de l'objet Array :

```js
const args = Array.from(arguments);

```

On peut par exemple définir la fonction sum en utilisant la méthode from :

```js
function sum(){
  const args = Array.from(arguments);
  
  return args.reduce( (acc, curr) => acc + curr );
}

console.log( sum(1,2,3,5) ); // 11

```

### Les fonctions fléchées <a class="anchor" id="section77"></a>

Les fonctions fléchées (arrow function) permettent d'avoir une syntaxe plus courte pour définir facilement des fonctions de rappel. On les utilise dans les fonctions JS telles que map, reduce, filter, ...

```js
const power2 = (x) => {
  return x ** 2 ;
};
const numbers = [1, 2, 5];
console.log(numbers.map( power2 ));
// [1, 4, 25]
```

Si vous ne retournez qu'une seule valeur, vous pouvez écrire la syntaxe suivante :

```js
// syntaxe consise
const sum = (x, y) => x + y ;
```

Dans le cas où vous souhaiteriez retourner un unique littéral, utilisez la syntaxe suivante (expression) :

```js
// syntaxe consise
const model = (x, y) => ({ x, y }) ;
console.log(model(1,2)); // retournera { x : 1, y : 2 }

// Une syntaxe plus longue mais équivalente
const model2 = (x, y) => { 
    return { x : x, y : y }
}
```

Contrairement aux fonctions classiques, les fonctions fléchées ne re-définissent pas de this. Si vous vous référez dans une fonction fléchée au mot clé this, la fonction fléchée **récupérera le this du contexte** dans lequel elle a été définie.

```js
const School = {
    name: "Alan",
    sayHello() {
        // récupérer le this du context
        const that = this;
        function getName() {
            console.log(that.name); // Alan
            console.log(this.name); // undefined
        }
        getName();
    },

    sayHelloArrowFunc(){
        // La fonction fléchée récupère le context de l'objet courant School
        let func = () => {
            console.log(this.name); // Alan
        }
        func();
    }
}
School.sayHello();
School.sayHelloArrowFunc();
```

### Fonction constructeur  <a class="anchor" id="section78"></a>

Une fonction classique peut définir un constructeur, **pas une fonction flèchée**. Par convention le nom de la fonction commencera par une majuscule :

```js

function User(name){
  // constructeur
  this.name = name;

  console.log(this.name);
}

const u1 = new user("Alan");
const u2 = new user("Alan");

// Le code qui suit produira une erreur 
// pas de constructeur dans ce cas
/*const userArrow = name => {
  this.name = name;

  console.log(this.name);
}

const uA1 = new userArrow("Alan");
const uA2 = new userArrow("Alan");
*/
```

Remarque : si vous appelez la fonction constructeur comme une fonction classique, alors le this sera de type "undefined" en mode strict.

```js
'use strict';

function User(name){
  console.log(this);
  this.name = name;
}

User('Alan'); // this undefined
```

Lorsque vous définissez une méthode dans un objet littéral, le this est l'objet littéral lui-même.

```js

const Model = {
    table : "Model",

    subModel:function(){
        console.log(this); // Objet model
    },

    // de manière totalement équivalente vous pour écrire ceci
    // pour définir une méthode/fonction
    subModel2(){
      console.log(this); // Objet model
    }
}

Model.subModel(); // this objet Model
```

### Exercice de synthèse corrigé un effet de bord <a class="anchor" id="section79"></a>

Comment éviter l'effet de bord sur la propriété this (undefined) dans le code suivant? Proposez une solution.

```js
const log = {
    count : 100,
    save: function () {
        'use strict';
        console.log(this.count);
    }
}
setTimeout(log.save, 500);
```

### Introduction à la notion de prototype pour une fonction  <a class="anchor" id="section7100"></a>

```js

const Student = {
  name : '',
  average : 17.5,
  situation: function(){
    console.log(`Name ${this.name} average : ${this.average}`);
  }
}
```

Cet objet possède une propriété **prototype**, elle listera l'ensemble des propriétés héritées depuis l'objet Student. La quasi-totalité des objets JS héritent de l'objet **Object** de JS.

```js
Student.__proto__
```

Vous pouvez dès lors appeler des méthodes, qui ne sont pas directement héritées dans l'objet Student.

#### (Application) Ajouter une propriété sur un constructeur <a class="anchor" id="section7101"></a>

Reprenons l'exemple précédent, nous allons voir comment ajouter une propriété au constructeur User qui sera partagée par toutes ses instances :

```js
'use strict';

function User(name, lastname){
  this.name = name;
  this.lastname = lastname;
}

let u1 = new User('Alan', 'Phi'); 

// On ajoute sur le constructeur lui-même la propriété
User.prototype.fullName = function (){

  return this.name + ' ' + this.lastname;
}

console.log(u1.fullName()); // Alan Phi
```

#### Exercice prototype average pour la fonction User <a class="anchor" id="section7102"></a>

Ajoutez la possibilité de définir l'âge dans la fonction constructeur User. Modifiez pour toutes les instances de User la fonction fullName pour qu'elle affiche le name, le fullName et l'âge d'un user.

Créez maintenant les 4 users suivants :

```js 
- Alan Phi age 45 ans notes : 15, 17, 13
- Bernad Lu age 78 ans notes : 11, 12, 9
- Sophie Boo age 56 ans notes : 10, 15, 11
- Alice Car age 45 ans notes : 5, 18, 20
```

Créez un nouveau prototype average dans la fonction constructeur User, qui calculera la moyenne des notes de chaque user.

Quand JS appelle cette méthode il ne la trouvera pas dans l'instance de User mais dans son prototype. Cette technique permet donc de créer des méthodes partagées par toutes les instances. Notez que vous pouvez tout à fait définir la méthode fullName après avoir fait son instance.

JS possède depuis **ES6** un mot clé class pour définir une classe, nous verrons qu'en fait ce mot clé permet de définir, comme dans l'exemple précédent, un constructeur.

## Quelques fonctions JS utiles pour le traitement des données  <a class="anchor" id="chapter8"></a>

### La fonction JS map <a class="anchor" id="section81"></a>

Vous pouvez utiliser une fonction fléchée sur des collections en utilisant des fonctions comme map, filter ou reduce par exemple :

- map retourne un tableau de même dimension que le tableau parcouru.

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const powerNumber = numbers.map( number => number ** 2);
```

#### Exercice puissance 3 <a class="anchor" id="section8101"></a>

Soit numbers une liste de nombres entiers, élevez uniquement à la puissance 3 les nombres pairs.

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
```

*Indications : pour calculer une puissance utilisez l'opérateur suivant*

```js
// opérateur puissance
2**3 // 8
```

- filter, il permet de filtrer des données dans un tableau en fonction d'un critère.

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

numbers.filter(number => number > 4);
// [5, 6, 7, 8, 9, 10]
```

- reduce, applique une fonction qui est un accumulateur et qui traite chaque valeur d'une liste de la gauche vers la droite afin de la réduire en une seule valeur. Vous pouvez passer en deuxième paramètre une valeur facultative.

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
// première paramètre fonction fléchée, deuxième paramètre val init de acc
const total = numbers.reduce((acc, curr) => curr + acc, 0);
console.log(total); // affiche 55

numbers.reduce((acc, curr) => curr + acc, 100);
// 155
```

#### Exercice max <a class="anchor" id="section8102"></a>

Reprenez l'objet numbers (array) de numériques et utilisez la méthode reduce pour calculer le max.

#### Exercice reduce sum impair <a class="anchor" id="section8103"></a>

Faites la somme des nombres impairs en utilisant la fonction reduce des valeurs suivantes :

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
```

#### Exercice fonction map sur un littéral <a class="anchor" id="section8104"></a>

Utilisez la fonction map pour calculer le prix TTC des téléphones. Utilisez une fonction fléchée.

```js
const phones = [
  { name: "iphone XX", priceHT: 900 },
  { name: "iphone X", priceHT: 700 },
  { name: "iphone B", priceHT: 200 },
];
```

## Affectation par décomposition <a class="anchor" id="chapter9"></a>

Vous pouvez affecter par décomposition des variables pré-définies comme suit :

```js
let a, b;
[a, b] = [10, 20];
```

Si vous ne souhaitez affecter que quelques variables et récupérer le reste de l'assignation dans un tableau, vous pouvez utiliser le spread operator :

```js
let a, b, rest;
[a, b, ...rest] = [10, 20, 30, 40, 50];
console.log(rest); // [30, 40, 50]
```

Vous pouvez également sauter des arguments dans l'assignation :

```js
let a, b;
[, , a, b] = [10, 20, 11, 111];

console.log(a, b); // 11 111
```

De même vous pouvez par décomposition assigner des valeurs à des variables en fonction des clés d'un littéral, vous devez cependant dans ce cas utiliser les mêmes noms de variable que les clés du littéral :

```js
const student = { mention: "AB", note: 12 };
const { mention, note } = student;

console.log(mention); // AB
console.log(note); // 12
```

Il est parfois intéressant de renommer les clés, dans ce cas il faudra utiliser la syntaxe suivante :

```js
const student = { mention: "AB", note: 12 };
const { mention: m, note: n } = student;

console.log(m); // AB
console.log(n); // 12
```

On peut également le faire par imbrication :

```js
const st = {
  name: "Antoine",
  family: {
    mother: "Yvette",
    father: "Michel",
    sister: "Sylvie",
  },
  age: 49,
};

const {
  name,
  family: { sister },
} = st;
```

Vous pouvez également destructurer un littéral en argument d'une fonction :

```js
const student = { mention: "AB", note: 12 };
const infoStudent = ({ mention, note }) => "info : " + mention + "note : " + note;

infoStudent(student);

//notez que vous pouvez également définir la fonction infoStudent sans vous souciez de l'ordre des clés :
const infoStudent_bis = ({ note, mention }) => "info : " + mention + "note : " + note;
```

### Exercice permutations <a class="anchor" id="section91"></a>

- Permutez les valeurs a et b suivantes :

```js
let a = 1, b = 2;
```

- Soient les trois variables a, b, et c permutez les valeurs dans l'ordre suivant :

- a <- b
- b <- c
- c <- a

```js
let a = 1, b = 2, c = 4;
```
