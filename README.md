# GStock Catalog — Catalogue Produits Open Source

> Catalogue de produits open-source pour les quincailleries et magasins de matériaux de construction en Algérie.
> Hébergé sur GitHub Pages, gratuit et accessible à tous.

## Qu'est-ce que c'est ?

Un catalogue de produits pré-rempli (ciment, fer, outillage, plomberie, électricité, peinture, quincaillerie, bois, sanitaire) que les utilisateurs de GStock peuvent importer en un clic. Au lieu de saisir manuellement des centaines de produits, un nouveau magasin peut démarrer avec un catalogue complet en quelques minutes.

## Structure du catalogue

```
docs/
├── index.html              ← Panel d'administration (SPA)
├── catalog/
│   ├── manifest.json       ← Index principal (version, catégories)
│   ├── categories.json     ← Définition des catégories
│   ├── brands.json         ← Définition des marques
│   ├── ciment-beton.json   ← Produits par catégorie
│   ├── fer-acier.json
│   ├── outillage.json
│   ├── plomberie.json
│   ├── electricite.json
│   ├── peinture.json
│   ├── quincaillerie.json
│   ├── bois-derives.json
│   └── sanitaire.json
└── images/                 ← Images produits
    ├── ciment/
    ├── fer/
    └── ...
```

## Catégories

| Catégorie | Produits | Exemples |
|-----------|----------|----------|
| 🏗️ Ciment & Béton | 24 | CPJ 42.5, CRC 32.5, béton tout prêt, colle carrelage |
| 🔩 Fer & Acier | 31 | Fer à béton Ø8-20, cornières, tubes, treillis soudé |
| 🔧 Outillage | 28 | Marteaux, tournevis, perceuses, meuleuses, niveaux |
| 🚿 Plomberie | 35 | Tubes PPR, raccords, robinets, soudure, flexibles |
| ⚡ Électricité | 40 | Câbles, disjoncteurs, prises, gaines, tableau |
| 🎨 Peinture | 22 | Peinture eau, glycéro, vernis, enduit, pinceaux |
| 🔨 Quincaillerie | 45 | Clous, vis, boulons, serrures, charnières, cadenas |
| 🪚 Bois & Dérivés | 18 | BA13, contreplaqué, aggloméré, MDF, lambris |
| 🚽 Sanitaire | 20 | WC, lavabos, éviers, douches, mitigeurs |

**Total : ~263 produits**

## Format JSON

### Produit

```json
{
  "code": "CIM-CPJ45-50KG",
  "name": "Ciment CPJ 42.5 Sac 50kg",
  "nameAr": "إسمنت CPJ 42.5 كيس 50كلغ",
  "brand": "GICA",
  "barcode": null,
  "unit": "SAC",
  "taxRate": 0.19,
  "costPrice": 850,
  "salePrice": 950,
  "resellerPrice": 920,
  "contractorPrice": 900,
  "minStock": 50,
  "image": "images/ciment/cpj-42-5-50kg.jpg",
  "aliases": ["ciment gris", "CPJ", "إسمنت رمادي"],
  "description": "Ciment Portland composé 42.5, sac de 50kg"
}
```

### Champs

| Champ | Type | Description |
|-------|------|-------------|
| `code` | string | Code unique du produit |
| `name` | string | Nom en français |
| `nameAr` | string | Nom en arabe |
| `brand` | string? | Marque (résolue à l'import) |
| `barcode` | string? | Code-barres EAN-13 |
| `unit` | string | Unité: PCE, SAC, M, KG, L, M², SET |
| `taxRate` | decimal | TVA: 0.19 (19%), 0.09 (9%), 0 (exonéré) |
| `costPrice` | decimal | Prix d'achat HT (DA) |
| `salePrice` | decimal | Prix de vente HT (DA) |
| `resellerPrice` | decimal? | Prix revendeur HT |
| `contractorPrice` | decimal? | Prix entrepreneur HT |
| `minStock` | decimal | Stock minimum |
| `image` | string? | Chemin vers l'image (relative) |
| `aliases` | string[] | Alias de recherche (fr/ar/derja) |
| `description` | string? | Description du produit |

## Contribution

Voir [CONTRIBUTING.md](CONTRIBUTING.md)

## Licence

MIT — Libre d'utilisation et de modification.
