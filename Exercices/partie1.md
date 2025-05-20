# NoSQL - Découverte en autonomie

Découverte en autonomie du NoSQL

## Ressources

- [SQL vs. NoSQL Databases: What’s the difference?](https://www.ibm.com/think/topics/sql-vs-nosql)
- [MongoDB - Data Modeling](https://www.mongodb.com/docs/manual/data-modeling/)
- [An Introduction to Document-Oriented Databases](https://www.digitalocean.com/community/conceptual-articles/an-introduction-to-document-oriented-databases)

## Contexte du projet

Tu as déjà manipulé des bases de données relationnelles (SQL) et connais leurs grands principes : schéma défini, tables, relations, langage SQL, etc.
Le monde des bases NoSQL propose une approche différente, souvent plus flexible et plus adaptée aux grands volumes de données ou aux structures moins rigides.

Dans ce cours, tu vas **découvrir en autonomie** ces différences entre SQL et NoSQL à travers **un travail de recherche** et **un exercice pratique** de modélisation. L’objectif est de comprendre dans quels cas NoSQL peut être préférable, comment on y stocke les données, et en quoi la modélisation diffère du relationnel.

Voici quelques liens utiles, mais ne te limite pas à cette sélection !

- [SQL vs. NoSQL Databases: What’s the difference?](https://www.ibm.com/think/topics/sql-vs-nosql)
- [MongoDB - Data Modeling](https://www.mongodb.com/docs/manual/data-modeling/)
- [An Introduction to Document-Oriented Databases](https://www.digitalocean.com/community/conceptual-articles/an-introduction-to-document-oriented-databases)

### Mise en pratique

Maintenant que tu as exploré la théorie, place à la pratique pour bien saisir la différence de pensée entre un modèle relationnel et un modèle NoSQL.

Tu souhaites stocker les informations d’un **catalogue de produits** : un produit possède un identifiant, un nom, une marque, un prix, une description, une ou plusieurs catégories (ayant chacune un identifiant et un nom), un stock, une date de création. En fonction de la catégorie, le produit aura des champs spécifiques (qui pourraient être la couleur et la taille pour un vêtement, ou le nombre de pages pour un livre, etc...).

Propose une **modélisation NoSQL** de trois produits.

Pour que tu voies comment on pourrait modéliser des données en NoSQL, voici un exemple de document JSON pour stocker un film ainsi que ses acteurs :

```json
{
  "_id": "64ac2fb1e819b22a4fd3d9a1",
  "title": "Avengers: Infinity War",
  "releaseYear": 2018,
  "actors": [
    {
      "name": "Robert Downey Jr.",
      "role": "Tony Stark / Iron Man"
    },
    {
      "name": "Chris Hemsworth",
      "role": "Thor"
    }
  ],
  "genres": ["Action", "Adventure", "Sci-Fi"],
  "runtime": 149,
  "language": "English"
}
```

- En SQL, on aurait fait plusieurs tables (`Film`, `Actor`, `FilmActor`, etc.).
- En NoSQL documentaire, on préfère souvent regrouper dans **un seul document** tout ce qui est pertinent pour un "film", quitte à dupliquer des informations.
