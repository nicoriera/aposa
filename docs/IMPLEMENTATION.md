# APOSA — Règles d'implémentation

## Priorités

1. Exactitude métier.
2. Clarté de la commande.
3. Accessibilité et mobile.
4. Performance média.
5. Direction artistique.
6. Exploitation simple par l'atelier.

## Architecture logicielle

- Commencer par un monolithe modulaire.
- Séparer domaine, application, intégrations et interface.
- Centraliser et auditer les transitions d'état.
- Utiliser des webhooks idempotents pour paiement et expédition.
- Stocker les montants dans la plus petite unité monétaire.
- Conserver les instantanés nécessaires sur les lignes de commande.

## Interface et commerce

- Concevoir mobile-first.
- Garder un appel principal par contexte.
- Traiter chargement, erreur, vide et succès.
- Ne jamais bloquer le paiement par une animation.
- Respecter `prefers-reduced-motion` et les standards d'accessibilité.
- Optimiser les médias et réserver leur espace.
- Répéter « précommande », clôture et expédition sur fiche, panier et confirmation.
- Ne jamais considérer une commande payée sur le seul retour navigateur.

## Données

- Collecter uniquement les données nécessaires.
- Séparer consentement marketing et messages transactionnels.
- Ne jamais journaliser secrets ou données de paiement.
- Définir conservation et suppression avant production.

## Tests minimums

Transitions d'édition, agrégation des achats, totaux, paiement réussi/échoué/remboursé, clôture, commande mobile sans compte, emails critiques, export de production et accessibilité du parcours principal.

## Definition of done

- Comportement testé selon son risque.
- États vides et erreurs utiles traités.
- Mobile vérifié.
- Documentation durable mise à jour.
- Aucune affirmation commerciale ou certification non sourcée.
