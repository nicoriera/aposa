# APOSA — Domaine et règles métier

## Cycle d'une édition

```text
DRAFT → TEASING → PREORDER_OPEN → PREORDER_CLOSED
      → SOURCING → PRODUCTION → FULFILMENT → ARCHIVED
```

| État | Vente | Fonction |
|---|---:|---|
| `DRAFT` | Non | Préparation privée |
| `TEASING` | Non | Révélation et inscription |
| `PREORDER_OPEN` | Oui | Commandes ouvertes |
| `PREORDER_CLOSED` | Non | Quantités figées |
| `SOURCING` | Non | Approvisionnement |
| `PRODUCTION` | Non | Pressage et contrôle |
| `FULFILMENT` | Non | Emballage et expédition |
| `ARCHIVED` | Non | Consultation définitive |

Les dates suggèrent les transitions, mais les changements sensibles doivent rester explicites et traçables.

## Entités

- **Edition** : numéro, concept, état, dates, expédition estimée, contenus et produits.
- **Product** : type, prix, caractéristiques, médias, fournisseur et fabrication.
- **Variant** : taille, couleur, référence fournisseur et quantité.
- **Order** : client, lignes, montants, paiement, production et expédition.
- **Production update** : étape, date, message et notification éventuelle.

## Invariants

- Une commande payée conserve les informations essentielles présentées à l'achat.
- Une édition archivée ne redevient pas achetable sans décision documentée.
- L'approvisionnement provient des commandes valides, agrégées par référence et variante.
- Annulation et remboursement corrigent les besoins tant que l'approvisionnement n'est pas figé.
- Un paiement échoué ne produit aucun besoin.
- L'estimation d'expédition affichée est enregistrée avec la commande.
- Les certifications sont rattachées à une référence et à une source.
- Les mesures du vêtement complètent les tailles S/M/L.
- La quantité finale archivée correspond à la production réelle.
