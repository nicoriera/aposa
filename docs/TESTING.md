# APOSA — Stratégie de tests

## Pyramide

### Tests unitaires

Couvrir les règles rapides et déterministes :

- transitions d'édition ;
- calculs de prix ;
- agrégation par variante ;
- éligibilité à une modification de taille ;
- statuts de commande et remboursement.

### Tests d'intégration

Couvrir base, transactions et adaptateurs :

- création de commande ;
- traitement idempotent d'un webhook ;
- fermeture et gel des besoins ;
- permissions administratives ;
- génération d'exports.

### Tests de contrat

Vérifier les schémas entre frontend, backend et prestataires. Utiliser les modes test officiels pour paiement, email et transport lorsque disponibles.

### Tests end-to-end

Limiter aux parcours critiques :

1. consulter l'édition et choisir une taille ;
2. commander sans compte ;
3. paiement refusé puis réussi ;
4. consulter une confirmation sécurisée ;
5. clôturer l'édition ;
6. exporter les besoins ;
7. publier une étape de production ;
8. expédier et suivre une commande.

## Cas limites obligatoires

- clôture pendant un panier actif ;
- double clic et double webhook ;
- taille ou prix modifié entre page et paiement ;
- remboursement avant et après gel d'approvisionnement ;
- prestataire email ou transport indisponible ;
- fuseau et changement d'heure ;
- retour arrière après paiement ;
- lien de commande expiré ou appartenant à un autre client.

## Données de test

- Utiliser des fabriques déterministes.
- Ne jamais utiliser de données client réelles.
- Couvrir accents, noms longs, adresses variées et tailles extrêmes.
- Figer l'horloge dans les tests dépendants des dates.

## Non-régression visuelle

Réserver les captures comparées aux composants et pages stables. Valider les changements intentionnels ; ne pas masquer une régression par une mise à jour globale des références.

## CI — à activer après choix de stack

Le pipeline minimal devra exécuter formatage, lint, types, tests unitaires, tests d'intégration essentiels, build et audit de dépendances. Les E2E critiques pourront s'exécuter sur preview ou avant mise en production.
