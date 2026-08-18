# Contribuer au Catalogue GStock

## Ajouter un produit

### Méthode 1 : Via le panel d'administration

1. Ouvrez https://gstock-dz.github.io/gstock-catalog/
2. Connectez-vous avec un token GitHub (accès mainteneur requis)
3. Sélectionnez une catégorie
4. Cliquez "Nouveau produit"
5. Remplissez les champs (nom FR, nom AR, prix, unité, etc.)
6. Uploadez une image si disponible
7. Sauvegardez

### Méthode 2 : Via Pull Request

1. Forkez le dépôt
2. Éditez le fichier JSON de la catégorie concernée (ex: `docs/catalog/ciment-beton.json`)
3. Ajoutez votre produit dans le tableau `products`
4. Uploadez l'image dans `docs/images/{categorie}/`
5. Soumettez une Pull Request

## Règles

### Produits

- **Code unique** : format `CAT-PRODUIT-TAILLE` (ex: `CIM-CPJ45-50KG`)
- **Nom FR** : obligatoire, clair et descriptif
- **Nom AR** : obligatoire, traduction naturelle (pas Google Translate)
- **Prix HT** : en Dinars Algériens (DA), prix de marché réaliste
- **Unité** : PCE, SAC, M, KG, L, M², SET, PAIR
- **TVA** : 0.19 (standard), 0.09 (réduit), 0 (exonéré)
- **Aliases** : 2-3 minimum, mélangeant français/arabe/derja

### Images

- Format : JPG
- Taille : 400x400px (carré)
- Poids : < 100KB
- Nom : `{code-produit}.jpg` (en minuscules, tirets)
- Source : photo personnelle, image fabricant, ou domaine public

### Marques

- Préférer les marques disponibles en Algérie (GICA, ENSA, Sonelgaz, Palsit, etc.)
- Pour les importés : Bosch, Makita, Stanley, Knauf, etc.

## Validation CI

Chaque Pull Request est automatiquement validée :
- JSON valide
- Codes produits uniques
- Champs obligatoires présents
- Prix positifs
- TVA valide (0, 0.09, ou 0.19)
- Images référencées existent
