 Types de Données en JavaScript

JavaScript possède deux grandes catégories de types de données :

Types primitifs (Primitives)

Types référence (Reference Types)

Chaque catégorie fonctionne différemment en mémoire, ce qui influence la manière dont les données sont copiées, comparées et manipulées.
  1. Types Primitifs

Les types primitifs sont des valeurs simples et immuables (ne changent pas directement).
Ils sont stockés par valeur, ce qui signifie que chaque variable reçoit une copie indépendante.

🔹 Liste des types primitifs :

string

number

boolean

null

undefined

bigint

symbol

  Exemples :
let nom = "Khadija";        // string
let age = 21;               // number
let isActive = true;        // boolean
let mission = null;         // null
let code;                   // undefined
let grandNombre = 12345678901234567890n; // bigint
let id = Symbol("userId");  // symbol

  2. Types Référence

Les types référence sont des structures complexes.
Ils sont stockés par référence, c’est-à-dire qu’une variable contient l’adresse de l’objet en mémoire, pas la valeur elle-même.

🔹 Types référence :

object

array

function

date

Map, Set, etc.

  Exemples :
let destination = { nom: "Moon Base Alpha", prix: 50000 }; // object
let reservations = ["Ali", "Sara", "Khadija"];             // array
let calculerPrix = function(p) { return p * 2; };          // function
let dateVoyage = new Date();                               // Date

 3. Différence Clé : Primitif vs Référence
✔ Copie d’un type primitif

Chaque variable contient sa propre valeur → indépendantes.

let a = 10;
let b = a; // copie
a = 20;

console.log(a); // 20
console.log(b); // 10 (reste inchangé)

✔ Copie d’un type référence

Les deux variables pointent vers le même objet.

let obj1 = { prix: 50000 };
let obj2 = obj1; // même référence

obj1.prix = 60000;

console.log(obj1.prix); // 60000
console.log(obj2.prix); // 60000 (même référence)

  4. Vérifier les types avec typeof

typeof permet d’identifier le type d’une variable.

 Syntaxe :
typeof variable;

✔ Exemples :
typeof "Mars";          // "string"
typeof 42;              // "number"
typeof true;            // "boolean"
typeof undefined;       // "undefined"
typeof 100n;            // "bigint"
typeof Symbol();        // "symbol"

typeof { a: 1 };        // "object"
typeof [1, 2, 3];       // "object" (attention !)
typeof function() {};   // "function"

  Note spéciale :

typeof null ➝ "object"
→ C’est un bug historique de JavaScript.

  5. Exemples dans le contexte d’un système de réservation (Space Odyssey)
✔ Types primitifs utilisés :
let client = "Yassine";            // string
let prixBase = 50000;              // number
let estDisponible = true;          // boolean
let description = null;            // null
let reduction;                     // undefined

✔ Types référence utilisés :
const reservation = {
  client: "Khadija",
  destination: "Mars Colony One",
  date: "2030-07-12"
};

const destinations = [
  "Moon Base Alpha",
  "Mars Colony One",
  "Europa Research Lab"
];

function calculerPrix(prix, jours) {
  return prix * jours;
}
