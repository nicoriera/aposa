# APOSA — Roadmap d'implémentation

La roadmap ordonne les décisions et validations ; elle ne fixe pas encore de dates.

Avant d'ouvrir la Phase 2, suivre la [check-list avant implémentation](PRE-IMPLEMENTATION.md) (Phases 0 et 1).

## Phase 0 — Cadrage du Drop 01

- Choisir le produit Stanley/Stella après prototypes.
- Définir tailles, coloris, coûts, prix et marge technique.
- Valider le contenu du colis et les délais fournisseur.
- Définir politique de précommande, livraison et retours.
- Produire l'identité et les contenus du Drop 01.

**Sortie** : fiche Drop 01 validée et prototype physique contrôlé.

## Phase 1 — Décisions techniques

- Comparer solution e-commerce et application sur mesure.
- Choisir paiement, emails, livraison, CMS, médias et hébergement.
- Définir budgets performance, niveaux de service et coûts.
- Compléter les ADR et le modèle de données.

**Sortie** : architecture exécutable sans choix implicite.

## Phase 2 — Fondations

- Initialiser la stack et la CI.
- Installer formatage, lint, types et tests.
- Créer design tokens et composants accessibles.
- Implémenter domaine des éditions, produits et variantes.
- Configurer secrets et environnements.

**Sortie** : application vide déployable et contrôlée.

## Phase 3 — Parcours public

- Edition active et archives.
- Fiche produit, galerie et guide des tailles.
- Atelier, aide et pages légales.
- Responsive, accessibilité, SEO et performance.

**Sortie** : découverte complète sans paiement.

## Phase 4 — Commerce

- Panier et revalidation serveur.
- Paiement et webhooks idempotents.
- Confirmation, emails et accès sécurisé à la commande.
- Annulation et remboursement.

**Sortie** : commande de bout en bout en environnement de test.

## Phase 5 — Atelier

- Back-office des éditions.
- Agrégation et gel d'approvisionnement.
- Export par référence, taille et couleur.
- Journal de production et notifications.
- Expédition et suivi.

**Sortie** : cycle opérationnel complet simulé.

## Phase 6 — Préparation du lancement

- Recette fonctionnelle et visuelle.
- Revue sécurité et confidentialité.
- Tests de charge proportionnés à la campagne.
- Sauvegarde, observabilité et runbooks.
- Commandes pilotes et répétition de la clôture.

**Sortie** : go/no-go formalisé pour le Drop 01.

## Phase 7 — Lancement et apprentissage

- Surveillance de l'ouverture à l'expédition.
- Communication transparente sur les étapes.
- Bilan produit, technique et atelier.
- Mise à jour des coûts, procédures et ADR.

**Sortie** : décisions du Drop 02 fondées sur des données réelles.
