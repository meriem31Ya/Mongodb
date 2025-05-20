## 📚 Exercices pratiques — Gestion d’une bibliothèque

### 📘 Exercice 1 : Insertion

- Insérer 3 nouveaux livres avec les champs `title`, `author`, `year`, `languages` (tableau).
- Utiliser la méthode `insert()` pour insérer les données dans la table `livres`.
  db.livres.insertMany([
  {
  title: "Le Comte de Monte-Cristo",
  author: "Alexandre Dumas",
  year: 1845,
  languages: ["Français", "Anglais", "Espagnol", "Allemand"]
  },
  {
  title: "La Métamorphose",
  author: "Franz Kafka",
  year: 1915,
  languages: ["Allemand", "Français", "Italien"]
  },
  {
  title: "L'Alchimiste",
  author: "Paulo Coelho",
  year: 1988,
  languages: ["Portugais", "Français", "Anglais", "Arabe"]
  }
  ]);

### 📖 2 : Lecture

- Afficher tous les livres.
- Afficher uniquement les titres et les auteurs.
- Afficher les livres publiés entre 1900 et 1950.
- Compter les livres écrits par "Albert Camus".

## 📊 3. Requêtes avec conditions

5. Rechercher les livres publiés en **1988**.
6. Trouver les livres publiés **après l’an 2000**.
7. Rechercher les livres disponibles en **anglais**.
8. Trouver les livres disponibles en **français ou en arabe**.
9. Trouver les livres écrits par **Victor Hugo** ou **Albert Camus**.
10. Trouver les livres **ne contenant pas** la langue **espagnole**.

### ✏️ 4 : Mise à jour

- Modifier l’auteur d’un livre.
- Renommer le champ `year` en `publication_year`.
- Ajouter "Turque" dans le tableau `languages` du livre L'Alchimiste.
- Supprimer le champ `languages` du livre La Métamorphose.

---

### 🗑️ 5 : Suppression

- Supprimer un livre par son titre.
- Supprimer tous les livres publiés avant 1900.

### 🔄 6 : Bonus

- Remplacer entièrement un livre par un nouveau document (livre).
- Utiliser `$pull` pour retirer une langue d’un tableau .

## 📊 7. Requêtes d'agrégation (niveau avancé)

- Compter le **nombre de livres par auteur**.
- Trouver les livres dont le **titre contient le mot "peste"** (insensible à la casse).
- Rechercher les livres avec une **description contenant "roman"**.
- Afficher les livres avec **plus d’une langue** disponible.
- Rechercher les livres avec **exactement 3 langues** dans le champ `languages`.
- Lister toutes les **langues** utilisées dans les livres avec leur fréquence.
- Regrouper les livres par **année de publication** et trier les années par **nombre de livres décroissant**.

  > 💡 Tu peux tester chaque commande dans `mongosh` après avoir fait `use library`
