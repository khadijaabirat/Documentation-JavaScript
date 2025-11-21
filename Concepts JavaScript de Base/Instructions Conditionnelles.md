 Instructions Conditionnelles en JavaScript
Les instructions conditionnelles permettent à votre programme d’exécuter du code uniquement si certaines conditions sont remplies.
Elles sont essentielles pour contrôler la logique d’un système : validation, disponibilité, prix, accès, restrictions, etc.

 1. if / else if / else
🔷 Définition
L’instruction if exécute un bloc de code si la condition est évaluée à true.
else if ajoute des conditions supplémentaires.
else s’exécute quand aucune condition n’est remplie.
✔ Syntaxe :
if (condition) {
  // code
} else if (autreCondition) {
  // code
} else {
  // code
}


  Exemple — Space Odyssey Reservation System
let places = 5;

if (places > 10) {
  console.log("De nombreuses places sont disponibles !");
} else if (places > 0) {
  console.log("Dernières places restantes !");
} else {
  console.log("Toutes les places sont réservées.");
}


  2. Instruction conditionnelle ternaire
🔷 Définition
C’est une version courte du if/else, utile pour affecter des valeurs.
✔ Syntaxe :
condition ? valeurSiVrai : valeurSiFaux;

 Exemple — Space Odyssey
let prix = 120000;
let reduction = prix > 100000 ? "Réduction appliquée" : "Pas de réduction";

console.log(reduction);


 3. switch
🔷 Définition
switch permet de comparer une valeur à plusieurs cas possibles.
Très utile lorsque les conditions sont multiples et basées sur une seule variable.
✔ Syntaxe :
switch (valeur) {
  case x:
    // code
    break;
  case y:
    // code
    break;
  default:
    // code
}


 Exemple — Space Odyssey
let destination = "Mars Colony One";

switch (destination) {
  case "Moon Base Alpha":
    console.log("Prix : 50 000$");
    break;
  
  case "Mars Colony One":
    console.log("Prix : 120 000$");
    break;
  
  case "Europa Research Lab":
    console.log("Prix : 80 000$");
    break;

  default:
    console.log("Destination inconnue.");
}


 4. Opérateurs de comparaison utilisés dans les conditions
OpérateurSignification==Égalité (conversion automatique)===Égalité stricte (recommandé)!=Différent!==Différent strict>Supérieur<Inférieur>=Supérieur ou égal<=Inférieur ou égal

 5. Exemples supplémentaires dans un système de réservation
✔ Vérifier si le client est majeur pour réserver :
let age = 16;

if (age >= 18) {
  console.log("Réservation autorisée.");
} else {
  console.log("Réservation refusée : âge minimum 18 ans.");
}


✔ Vérifier la disponibilité avant la réservation :
let disponible = true;

if (disponible) {
  console.log("Réservation confirmée !");
} else {
  console.log("Aucune place disponible.");
}


✔ Ternaires pour afficher un statut :
let statut = disponible ? "Ouvert" : "Complet";
console.log(`Statut du vol : ${statut}`);


✔ Switch pour les niveaux d'accès des destinations :
let level = 2;

switch (level) {
  case 1:
    console.log("Accès : Orbite terrestre");
    break;
  case 2:
    console.log("Accès : Lune");
    break;
  case 3:
    console.log("Accès : Mars");
    break;
  default:
    console.log("Accès non défini");
}


  Résumé Professionnel
InstructionUtilitéif / else if / elseLogique flexible, conditions multiplesternaireVersion courte pour expressions simplesswitchIdéal pour tester plusieurs valeurs d’une même variable

