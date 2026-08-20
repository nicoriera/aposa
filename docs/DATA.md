# APOSA — Données

## Modèle conceptuel

```text
Edition 1──n Product 1──n Variant
Customer 1──n Order 1──n OrderLine
Edition 1──n ProductionUpdate
Order 1──n PaymentEvent
Order 1──n Shipment
```

## Données immuables ou historisées

Conserver dans la commande les instantanés nécessaires :

- nom du produit et de la variante ;
- prix, taxe et devise ;
- estimation d'expédition affichée ;
- caractéristiques contractuelles essentielles ;
- adresses utilisées ;
- consentements pertinents et version des conditions acceptées.

Les mises à jour du catalogue ne doivent pas réécrire l'historique d'une commande.

## Données sensibles

- Ne jamais stocker de numéro de carte ou cryptogramme.
- Réduire la conservation des adresses et coordonnées au besoin légal et opérationnel.
- Chiffrer les secrets et données sensibles selon l'infrastructure retenue.
- Restreindre l'accès administratif par rôle et journaliser les actions sensibles.

## Migrations

- Versionner toutes les migrations.
- Prévoir sauvegarde et retour arrière pour les changements destructifs.
- Déployer les changements incompatibles en plusieurs étapes.
- Tester les migrations sur une copie non sensible ou des données synthétiques.

## Sauvegardes

Définir avant production : fréquence, rétention, chiffrement, restauration testée, RPO et RTO. Une sauvegarde non restaurée en test n'est pas considérée fiable.

## Rétention

Créer une matrice documentée pour commandes, factures, comptes, logs, paniers abandonnés, analytics et consentements lorsque les obligations juridiques et la stack seront confirmées.
