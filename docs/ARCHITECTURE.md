# APOSA — Architecture fonctionnelle

## Navigation MVP

```text
Edition actuelle | Archives | Atelier | Panier
```

Le compte, l'aide, le contact et les pages légales restent secondaires. Le compte n'est pas obligatoire pour acheter.

## Edition actuelle

1. Visuel manifeste.
2. Nom, prix, statut et clôture.
3. Produit, taille et précommande.
4. Histoire du graphisme.
5. Recto, verso et détails.
6. Textile, coupe et grammage.
7. Packaging et objets inclus.
8. Fabrication à Lorient.
9. Calendrier de production.
10. Guide des tailles, engagements et FAQ.

## Autres surfaces

- **Archives** : quantité, dates, œuvre, matière, technique et packaging, sans achat.
- **Atelier** : manifeste, équipe, machines, processus, partenaires et engagements.
- **Compte** : commandes, production, facture, colis, contact et retours.

## Back-office

- Créer et publier une édition.
- Gérer produits, variantes, médias et contenus.
- Piloter les états.
- Agréger et exporter les besoins par référence, couleur et taille.
- Publier les étapes de fabrication.
- Préparer les expéditions et archiver l'édition.

## Modules logiques

```text
Editions / Catalog
Checkout / Payments
Customers / Accounts
Orders
Production planning
Fulfilment / Shipping
Content / Media
Notifications
Compliance / Consent
Observability
```

Ces modules sont des responsabilités, pas des services séparés. Commencer par une application modulaire simple et éviter les microservices.

## Intégrations à décider

Paiement, emails, livraison, CMS, médias, analytics et consentement. Documenter chaque choix structurant dans `docs/DECISIONS.md`.
