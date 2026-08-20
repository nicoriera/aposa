# Risk and review checklist

## Classer le risque

- **Faible** : documentation, copie, style isolé.
- **Moyen** : composant, contenu administrable, endpoint non critique.
- **Élevé** : paiement, commande, auth, données, migrations, clôture, sécurité ou production.

## Vérifier pour toute tâche

- Le comportement respecte-t-il `DOMAIN.md` ?
- Les contrats modifiés sont-ils documentés ?
- Les erreurs et états vides sont-ils traités ?
- Les tests sont-ils proportionnés au risque ?
- La documentation durable est-elle à jour ?

## Ajouter pour un risque élevé

- Cas de concurrence et rejeu.
- Autorisation et confidentialité.
- Reprise après panne.
- Observabilité et runbook.
- Migration et retour arrière.
- Revue manuelle du diff complet.
