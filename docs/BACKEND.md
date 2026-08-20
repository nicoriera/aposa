# APOSA — Architecture backend

## Responsabilité

Le backend garantit les règles d'édition, les prix, les commandes, l'approvisionnement, le paiement, les notifications et l'expédition.

## Style d'architecture

Commencer par un monolithe modulaire avec des limites explicites :

```text
Edition
Catalog
Cart and Pricing
Order
Payment
Production
Fulfilment
Customer
Content
Notification
Audit
```

Chaque module expose une interface applicative et protège ses invariants. Ne créer un service séparé qu'après une contrainte mesurée de sécurité, disponibilité ou charge.

## Couches

- **Domain** : entités, valeurs, invariants et transitions.
- **Application** : cas d'usage et transactions.
- **Infrastructure** : base, paiement, emails, stockage et transporteur.
- **Delivery** : HTTP, webhooks, tâches et administration.

## Transactions critiques

- Ouvrir ou clôturer une édition.
- Créer une intention de paiement à partir d'un panier revalidé.
- Confirmer une commande depuis un événement signé du prestataire.
- Rembourser et corriger l'approvisionnement.
- Figer les besoins avant commande fournisseur.
- Publier une étape de production.
- Créer une expédition et enregistrer son suivi.

## Idempotence et concurrence

- Attribuer une clé d'idempotence aux commandes externes rejouables.
- Stocker l'identifiant unique des événements reçus.
- Empêcher deux confirmations pour un même paiement.
- Protéger la clôture et le gel d'approvisionnement par transaction ou verrou adapté.
- Concevoir les tâches asynchrones pour être rejouables.

## Erreurs

- Utiliser des erreurs métier stables et traduisibles.
- Ne pas exposer stack traces, secrets ou détails fournisseur.
- Distinguer validation, conflit, authentification, autorisation et panne externe.
- Corréler les logs sans y stocker de données sensibles.

## Tâches asynchrones

- emails ;
- traitement des webhooks ;
- génération d'exports ;
- synchronisation transporteur ;
- optimisation média si nécessaire.

Documenter retries, délais, dead-letter et intervention manuelle avant production.
