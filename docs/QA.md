# APOSA — Assurance qualité

## Objectif

Vérifier que l'expérience est correcte pour le client et exploitable par l'atelier, au-delà du simple fonctionnement technique.

## Risques prioritaires

1. Commande acceptée après clôture.
2. Mauvais prix, produit ou taille.
3. Paiement confirmé sans commande ou inversement.
4. Quantités fournisseur erronées.
5. Délai de précommande ou d'expédition ambigu.
6. Parcours mobile ou clavier bloqué.
7. Email ou suivi révélant les données d'un autre client.
8. Affirmation environnementale ou certification incorrecte.

## Matrice de couverture

Chaque fonctionnalité doit être évaluée sur :

- règle métier ;
- cas nominal ;
- erreur et reprise ;
- mobile et desktop ;
- clavier et lecteur d'écran lorsque pertinent ;
- performance ;
- sécurité et confidentialité ;
- observabilité ;
- impact atelier et support.

## Environnements

- **Local** : développement et tests rapides avec services simulés.
- **Preview** : validation de chaque pull request avec données synthétiques.
- **Staging** : parcours complet avec modes test des prestataires.
- **Production** : données réelles, accès restreint et changements contrôlés.

Ne jamais copier des données personnelles de production dans un environnement inférieur.

## Recette d'une édition

Avant ouverture :

- contenus et prix approuvés ;
- toutes les tailles et mesures vérifiées ;
- dates et fuseau vérifiés ;
- paiement test réussi et échoué ;
- emails relus ;
- clôture automatique et manuelle testée ;
- export d'approvisionnement validé ;
- mobile, clavier et performance contrôlés ;
- procédure de support connue.

## Sévérité des défauts

- **S0 critique** : sécurité, perte de données ou encaissement incohérent ; blocage du lancement.
- **S1 majeure** : commande impossible ou règle métier violée ; blocage du lancement.
- **S2 moyenne** : dégradation avec contournement ; correction planifiée.
- **S3 mineure** : cosmétique sans impact fonctionnel ; arbitrage produit.

## Preuves

Une validation doit citer le scénario, l'environnement, le résultat et, pour le visuel, fournir une capture pertinente. « Ça marche » n'est pas une preuve suffisante.
