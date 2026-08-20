# APOSA — Contrats API

## Principes

- Contrats versionnés ou évolutifs sans rupture implicite.
- Validation stricte des entrées et réponses stables.
- Identifiants opaques côté public.
- Dates au format ISO 8601 avec fuseau.
- Montants sous forme d'entiers avec devise explicite.
- Pagination pour toute collection non bornée.
- Erreurs structurées avec code stable, message public et identifiant de corrélation.

## Ressources initiales

```text
GET  /api/editions/current
GET  /api/editions/:slug
GET  /api/products/:id
POST /api/cart/validate
POST /api/checkout/session
GET  /api/orders/:reference
POST /api/webhooks/payment
POST /api/webhooks/shipping
```

Cette liste décrit les besoins, pas le framework ni le protocole définitif.

## Exemple d'erreur

```json
{
  "error": {
    "code": "PREORDER_CLOSED",
    "message": "Cette édition n'est plus disponible en précommande.",
    "requestId": "req_opaque"
  }
}
```

## Authentification et autorisation

- Consultation publique des éditions.
- Accès à une commande par session authentifiée ou jeton opaque limité et expirant.
- Administration protégée par authentification forte et contrôle de rôle.
- Webhooks vérifiés par signature et protection anti-rejeu.

## Compatibilité

Avant toute rupture : documenter la décision, migrer les consommateurs et prévoir une période de compatibilité lorsque nécessaire.
