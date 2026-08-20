---
name: aposa-project
description: Plan and implement APOSA product, UX, commerce, content, data, and engineering changes while enforcing the project's preorder model, edition lifecycle, ethical-claim boundaries, documentation, and mobile-first quality rules. Use for any task in the APOSA repository that affects product behavior, site structure, checkout, editions, orders, production, fulfilment, customer communication, branding implementation, or architecture decisions.
---

# Aposa Project

Appliquer le cadre produit APOSA avant de modifier le dépôt. Préserver le modèle de précommande, la simplicité du parcours et la traçabilité des décisions.

## Démarrage obligatoire

1. Lire `AGENTS.md` à la racine.
2. Lire les documents pertinents dans `docs/`.
3. Identifier les règles métier et états affectés.
4. Vérifier si une décision structurante manque dans `docs/DECISIONS.md`.

Pour une tâche produit ou UX, lire `references/product-checklist.md`.
Pour une tâche d'implémentation, lire `references/engineering-checklist.md`.

## Workflow

### Cadrer

- Reformuler l'objectif utilisateur et l'objectif atelier.
- Distinguer ce qui est validé de ce qui reste hypothétique.
- Refuser d'inventer prix, délais, certifications ou caractéristiques.
- Préserver la précommande sans stock comme modèle par défaut.

### Concevoir

- Rendre produit, taille, prix, clôture et expédition immédiatement compréhensibles.
- Garder les interactions expérimentales hors du chemin critique d'achat.
- Prévoir les états de l'édition avant de dessiner une page statique.
- Concevoir d'abord le parcours mobile.

### Implémenter

- Placer les règles métier dans le domaine.
- Centraliser et tester les transitions d'état.
- Rendre les intégrations externes remplaçables.
- Gérer l'idempotence pour paiement et expédition.
- Ne pas ajouter de complexité sans besoin mesuré.

### Vérifier

- Tester le cas nominal et les échecs critiques.
- Vérifier mobile, accessibilité et performances média.
- Vérifier l'approvisionnement après paiement, annulation et remboursement.
- Mettre à jour les documents affectés dans la même modification.

## Contraintes commerciales

- Ne jamais afficher de faux stock ou de faux compte à rebours.
- Afficher « précommande », clôture et expédition avant paiement.
- Ne pas obliger la création d'un compte.
- Conserver les informations contractuelles essentielles avec la commande.
- Ne pas supprimer un droit consommateur sur la seule base d'une fabrication après commande.

## Contraintes de marque

- Rester minimal, graphique, précis et lisible.
- Utiliser la direction artistique comme système, pas comme décoration du checkout.
- Traiter vêtement, tirage, packaging et objet comme une même édition.
- Attribuer chaque engagement et certification à sa source exacte.
