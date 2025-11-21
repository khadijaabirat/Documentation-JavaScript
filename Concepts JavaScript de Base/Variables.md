 
  Variables : var, let, const 
1. var
🔷 Définition

var est le mot-clé historique de JavaScript utilisé pour déclarer des variables.
Il possède un scope fonctionnel (function scope), ce qui signifie qu’il ignore les blocs { }.
Les variables déclarées avec var peuvent être réassignées et redéclarées sans provoquer d’erreur.

🔷 Caractéristiques

✔ Hoisting (remontée en haut du scope)

✔ Redéclaration possible

✔ Réassignation possible

❌ Pas de block scope → peut créer des comportements inattendus

❌ Déconseillé dans le code moderne

  Exemple
var placesDisponibles = 50;

if (true) {
  var placesDisponibles = 30; // La même variable !
}

console.log(placesDisponibles); // 30

2. let
🔷 Définition

let permet de déclarer des variables avec un scope de bloc (block scope).
La variable peut être modifiée (réassignée), mais ne peut pas être redéclarée dans le même bloc.

🔷 Caractéristiques

✔ Block scope

✔ Réassignation possible

❌ Redéclaration impossible

❌ Pas utilisable avant définition (temporal dead zone)

  Exemple
let passengers = 10;

if (true) {
  let passengers = 5; // Variable différente dans le bloc
  console.log(passengers); // 5
}

console.log(passengers); // 10

3. const
🔷 Définition

const déclare une variable qui ne peut pas être réassignée après son initialisation.
Comme let, elle possède un scope de bloc.

🔷 Caractéristiques

✔ Block scope

❌ Pas de réassignation

❌ Redéclaration impossible

✔ Obligation de donner une valeur dès la création

⚠ Les objets et tableaux peuvent être modifiés (mutation autorisée)

  Exemple
const prixFixe = 50000;
// prixFixe = 60000; ❌ Erreur

const destination = { nom: "Moon Base Alpha" };
destination.nom = "Mars Colony One"; // ✔ Mutation possible

  4. Quand utiliser var, let, const ?
✔ Utiliser const par défaut

Pour toutes les valeurs qui ne changent pas.

Pour les objets & tableaux dont la référence doit rester la même.

✔ Utiliser let quand la valeur doit changer

Compteurs

États d’un système (ex. utilisateur connecté, nombre de places disponibles)

Variables de boucles

  Éviter var

Sauf si vous travaillez sur du code très ancien.

Son scope est imprévisible et peut créer des bugs.

 5. Exemples dans un système de réservation — Space Odyssey
✔ const — données fixes
const PRIX_PAR_DESTINATION = {
  "Moon Base Alpha": 50000,
  "Mars Colony One": 120000,
  "Europa Research Lab": 80000
};

✔ let — valeurs qui évoluent
let placesRestantes = 20;

function reserverPlace() {
  if (placesRestantes > 0) {
    placesRestantes--; // la valeur change
  }
}

reserverPlace();
console.log(placesRestantes); // 19

✔ var — à éviter, mais exemple éducatif
var nomClient = "Khadija";

function changerNom() {
  var nomClient = "Sara"; // redéclaration permise
  console.log(nomClient);  // "Sara"
}

changerNom();
console.log(nomClient);    // "Khadija"
