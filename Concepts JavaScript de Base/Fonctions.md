Devoir de Documentation JavaScript

1. Déclarations de fonction vs Expressions de fonction
    1.1 Déclaration de fonction (Function Declaration)
Une déclaration de fonction est une fonction définie avec le mot-clé function.
Elle est hoistée, ce qui signifie qu’elle peut être appelée avant sa définition dans le code.
Ce type de fonction est souvent utilisé pour des opérations principales ou globales.
✔ Exemple — Space Odyssey
Créer une réservation pour une destination spatiale :
// Déclaration de fonction
function creerReservation(nomClient, destination, date) {
  return {
    client: nomClient,
    destination: destination,
    date: date,
    statut: "confirmée"
  };
}

   1.2 Expression de fonction (Function Expression)
Une expression de fonction est une fonction assignée à une variable.
Elle n’est pas hoistée, donc elle doit être définie avant utilisation.
On l’utilise souvent lorsque la fonction doit être stockée, passée en argument ou modulée.
✔ Exemple — Space Odyssey
Calculer le prix d’un voyage spatial selon la destination :
// Expression de fonction
const calculerPrix = function (destination, jours) {
  const tarifs = {
    "Moon Base Alpha": 50000,
    "Mars Colony One": 120000,
    "Europa Research Lab": 80000,
  };

  return tarifs[destination] * jours;
};

// Utilisation
const prix = calculerPrix("Mars Colony One", 3);


2. Fonctions fléchées (Arrow Functions)
   2.1 Définition
Les fonctions fléchées introduisent une syntaxe plus concise.
Elles n’ont pas leur propre this, ce qui les rend idéales pour les callbacks, les opérations sur les tableaux ou les fonctions courtes.
✔ Exemple — Space Odyssey
Filtrer les réservations pour une date spécifique :
// Fonction fléchée
const filtrerReservations = (reservations, date) =>
  reservations.filter(res => res.date === date);

// Exemple d'utilisation
const allReservations = [
  { client: "Ali", destination: "Moon Base Alpha", date: "2030-05-12" },
  { client: "Sara", destination: "Mars Colony One", date: "2030-05-13" },
  { client: "Khadija", destination: "Moon Base Alpha", date: "2030-05-12" },
];

const result = filtrerReservations(allReservations, "2030-05-12");


 Conclusion
Ces trois types de fonctions sont essentiels dans l’application Space Odyssey :


Les déclarations définissent les actions principales (réservation).


Les expressions permettent de gérer des calculs ou des opérations précises (prix).


Les fonctions fléchées simplifient les manipulations de listes (filtres, recherches…).



