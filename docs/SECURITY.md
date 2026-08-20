# APOSA — Sécurité et confidentialité

## Modèle de menace initial

Actifs à protéger :

- données clients et adresses ;
- commandes, remboursements et exports ;
- comptes administrateurs ;
- secrets des prestataires ;
- contenus non publiés des éditions ;
- intégrité des prix, dates et statuts.

Menaces principales : accès horizontal à une commande, prise de contrôle admin, falsification de webhook, injection, fuite de secret, abus de remboursement, dépendance compromise et collecte excessive.

## Règles obligatoires

- Ne jamais faire confiance aux prix ou statuts envoyés par le client.
- Vérifier authentification et autorisation à chaque accès protégé.
- Utiliser des identifiants publics non séquentiels ou non devinables.
- Vérifier les signatures de webhooks et empêcher leur rejeu.
- Valider et normaliser les entrées côté serveur.
- Encoder les sorties selon leur contexte.
- Protéger les mutations contre les requêtes intersites selon l'architecture retenue.
- Appliquer des limites de débit aux endpoints sensibles.
- Garder secrets et fichiers `.env` hors du dépôt.
- Utiliser les en-têtes HTTP de sécurité adaptés.

## Authentification

- Compte client facultatif.
- Administration avec MFA obligatoire lorsque le fournisseur le permet.
- Sessions courtes pour l'administration, rotation et révocation possibles.
- Aucun secret d'administration transmis par email en clair.

## Paiement

- Déléguer la saisie des cartes à un prestataire conforme.
- Ne jamais stocker les données carte.
- Confirmer une commande depuis un événement serveur signé.
- Contrôler montant, devise et référence interne avant confirmation.
- Journaliser remboursements et actions administratives.

## Dépendances et supply chain

- Fichier de verrouillage obligatoire après choix du gestionnaire.
- Mises à jour automatisées et revues après choix de stack.
- Refuser les dépendances abandonnées ou injustifiées.
- Exécuter les outils de build avec le minimum de permissions.
- Épingler les actions CI à une version ou un commit de confiance.

## Logs et incidents

- Ne pas loguer mots de passe, tokens, adresses complètes ou données de paiement.
- Utiliser des identifiants de corrélation.
- Définir un canal de signalement avant ouverture publique.
- Isoler, révoquer, corriger, notifier et documenter tout incident selon son impact.

## Revue sécurité

Avant production : revue des accès, secrets, webhooks, endpoints de commande, permissions admin, politiques de données, sauvegardes et dépendances. Refaire cette revue avant chaque nouveau prestataire critique.
