# APOSA — Exploitation et mise en production

## Principes

- Automatiser les opérations répétables sans cacher les étapes métier.
- Préférer une intervention manuelle sûre à une automatisation fragile.
- Rendre chaque opération critique observable et réversible lorsque possible.

## Environnements et secrets

- Configurations séparées par environnement.
- Secrets fournis par la plateforme, jamais par Git.
- Prestataires en mode test hors production.
- Accès production limités et révisés régulièrement.

## Déploiement

Le pipeline cible doit :

1. valider code et migrations ;
2. construire un artefact reproductible ;
3. déployer une preview ;
4. permettre une validation ;
5. déployer en production avec journal ;
6. vérifier la santé après déploiement ;
7. permettre un rollback documenté.

## Observabilité

Mesurer sans exposer de données personnelles :

- erreurs frontend et backend ;
- latence et taux d'erreur des endpoints ;
- webhooks échoués ou rejoués ;
- commandes bloquées entre paiement et confirmation ;
- files de tâches et emails échoués ;
- statut des sauvegardes ;
- disponibilité des prestataires critiques.

## Runbooks requis avant le Drop 01

- paiement confirmé sans commande ;
- commande sans email ;
- clôture impossible ;
- erreur d'export fournisseur ;
- rupture fournisseur après clôture ;
- remboursement ;
- retard de production ;
- incident de sécurité ;
- indisponibilité du site pendant une précommande.

## Lancement d'une édition

- Gel des changements non essentiels avant ouverture.
- Sauvegarde et vérification des prestataires.
- Responsables identifiés pour commerce, technique et communication.
- Surveillance renforcée à l'ouverture et à la clôture.
- Bilan après l'expédition : incidents, coûts réels, conversion et améliorations.
