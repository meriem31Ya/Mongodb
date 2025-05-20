# 📦 Modélisation NoSQL - Catalogue de Produits

## 🧾 Contexte

Chaque produit a :

- Un identifiant
- Un nom
- Une marque
- Un prix
- Une description
- Une ou plusieurs catégories (avec un id et un nom)
- Un stock
- Une date de création
- Des champs spécifiques selon la catégorie (taille, couleur, nombre de pages, etc.)

---

## 🧩 Exemple de modélisation NoSQL (MongoDB / JSON)

### 1. 👕 Produit : T-shirt

```json
{
  "_id": "prod001",
  "name": "T-shirt coton bio",
  "brand": "GreenWear",
  "price": 19.99,
  "description": "T-shirt 100% coton bio, coupe classique.",
  "categories": [{ "id": "cat01", "name": "Vêtements" }],
  "stock": 150,
  "createdAt": "2024-05-01T10:00:00Z",
  "attributes": {
    "color": "Bleu",
    "size": "M"
  }
}
```
