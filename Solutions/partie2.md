# 📘 Exercice MongoDB : Manipulation de données

## 📘 1. Insertion

```js
db.livres.insertMany([
  {
    title: "Le Comte de Monte-Cristo",
    author: "Alexandre Dumas",
    year: 1845,
    languages: ["Français", "Anglais", "Espagnol", "Allemand"],
  },
  {
    title: "La Métamorphose",
    author: "Franz Kafka",
    year: 1915,
    languages: ["Allemand", "Français", "Italien"],
  },
  {
    title: "L'Alchimiste",
    author: "Paulo Coelho",
    year: 1988,
    languages: ["Portugais", "Français", "Anglais", "Arabe"],
  },
]);

// a) Tous les livres
db.livres.find();

// b) Titres et auteurs uniquement
db.livres.find({}, { title: 1, author: 1, _id: 0 });

// c) Livres publiés entre 1900 et 1950
db.livres.find({ year: { $gte: 1900, $lte: 1950 } });

// d) Compter les livres écrits par "Albert Camus"
db.livres.countDocuments({ author: "Albert Camus" });

// a) Livres publiés en 1988
db.livres.find({ year: 1988 });

// b) Livres publiés après 2000
db.livres.find({ year: { $gt: 2000 } });

// c) Livres disponibles en anglais
db.livres.find({ languages: "Anglais" });

// d) Livres en français ou arabe
db.livres.find({ languages: { $in: ["Français", "Arabe"] } });

// e) Livres écrits par Victor Hugo ou Albert Camus
db.livres.find({ author: { $in: ["Victor Hugo", "Albert Camus"] } });

// f) Livres ne contenant pas "Espagnol"
db.livres.find({ languages: { $ne: "Espagnol" } });

// a) Modifier l’auteur
db.livres.updateOne(
  { title: "Le Comte de Monte-Cristo" },
  { $set: { author: "A. Dumas" } }
);

// b) Renommer le champ year en publication_year
db.livres.updateMany({}, { $rename: { year: "publication_year" } });

// c) Ajouter "Turque" dans languages de L'Alchimiste, addTOset ne crée pas de doublon
db.livres.updateOne(
  { title: "L'Alchimiste" },
  { $addToSet: { languages: "Turque" } }
);

// d) Supprimer le champ languages de La Métamorphose
db.livres.updateOne(
  { title: "La Métamorphose" },
  { $unset: { languages: "" } }
);
// a) Supprimer un livre par titre
db.livres.deleteOne({ title: "La Métamorphose" });

// b) Supprimer tous les livres publiés avant 1900
db.livres.deleteMany({ publication_year: { $lt: 1900 } });

// a) Remplacer entièrement un livre
db.livres.replaceOne(
  { title: "L'Alchimiste" },
  {
    title: "L'Alchimiste - Nouvelle Édition",
    author: "Paulo Coelho",
    publication_year: 1993,
    languages: ["Français", "Anglais"],
  }
);

// b) Retirer une langue d’un tableau
db.livres.updateOne(
  { title: "L'Alchimiste - Nouvelle Édition" },
  { $pull: { languages: "Anglais" } }
);
// a) Nombre de livres par auteur

// b) Titre contenant "peste" (insensible à la casse)
db.livres.find({ title: { $regex: "peste", $options: "i" } });

// c) Description contenant "roman"
db.livres.find({ description: { $regex: "roman", $options: "i" } });

// d) Livres avec plus d’une langue
db.livres.find({ "languages.1": { $exists: true } });

// e) Livres avec exactement 3 langues
db.livres.find({ languages: { $size: 3 } });

// f) Fréquence des langues utilisées

// g) Regrouper par année de publication et trier
```
