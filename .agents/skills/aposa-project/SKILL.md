---
name: aposa-project
description: Plan, implement, test, review, secure, and operate APOSA product, design, frontend, backend, commerce, data, and documentation changes while enforcing the preorder model, edition lifecycle, ethical-claim boundaries, architecture contracts, QA gates, and agent workflow. Use for any APOSA repository task affecting product behavior, UX, APIs, orders, payments, production, fulfilment, customer data, deployment, security, testing, or technical decisions.
---

# Aposa Project

Appliquer le cadre produit APOSA avant de modifier le dépôt. Préserver le modèle de précommande, la simplicité du parcours et la traçabilité des décisions.

## Démarrage obligatoire

1. Lire `AGENTS.md` à la racine.
2. Lire `references/task-routing.md` et les documents qu'il indique.
3. Identifier les règles, contrats, données et états affectés.
4. Classer le risque avec `references/review-checklist.md`.
5. Vérifier si une décision structurante manque dans `docs/DECISIONS.md`.

Lire `references/product-checklist.md` pour le produit ou l'UX et `references/engineering-checklist.md` pour l'implémentation.

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
- Vérifier sécurité, données et exploitation selon le risque.
- Mettre à jour les documents affectés dans la même modification.

### Livrer

- Résumer le résultat visible avant les détails techniques.
- Nommer les tests exécutés et leurs résultats.
- Signaler les hypothèses, limites et décisions restantes.
- Vérifier le diff et l'état Git avant toute demande de commit.

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

## Garde-fous agents

- Ne pas déléguer la lecture ou l'interprétation de ce skill.
- Déléguer seulement des sous-tâches bornées sans chevauchement de fichiers.
- Ne jamais inventer une exigence manquante qui modifierait le produit.
- Ne pas publier, pousser, fusionner ou déployer sans autorisation explicite.
- Préserver les modifications existantes qui ne relèvent pas de la tâche.
