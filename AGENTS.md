# APOSA — Instructions for agents

## Mission

Construire APOSA comme un atelier lorientais d'éditions graphiques premium vendues en précommande, sans stock commercial permanent.

Avant toute modification, lire `.agents/skills/aposa-project/SKILL.md`, puis suivre son routage documentaire. `docs/README.md` est l'index et la source d'autorité documentaire.

## Principes non négociables

- Une édition est vendue pendant une fenêtre définie, puis produite après sa clôture.
- Ne jamais simuler une rareté par un faux stock ou un faux compteur.
- Afficher avant paiement le caractère de précommande, la clôture et le délai d'expédition.
- La commande doit rester accessible et prioritaire sur les effets graphiques.
- Concevoir mobile-first, avec une interface minimale, graphique et performante.
- Attribuer chaque certification et engagement à sa source exacte.
- Ne pas supposer qu'une fabrication après commande supprime les droits du consommateur.
- Ne pas figer une stack ou un prestataire sans décision documentée.
- Traiter paiement, authentification, données, migrations, clôture et production comme des changements à risque élevé.
- Ne jamais pousser, publier, fusionner, déployer ou modifier une ressource externe sans l'autorisation correspondante.

## Méthode

- Consigner les décisions durables dans `docs/DECISIONS.md`.
- Mettre à jour la documentation avec le code lorsque le domaine ou l'architecture change.
- Placer les règles métier dans le domaine, pas uniquement dans l'interface.
- Tester en priorité produit, taille, panier, paiement, confirmation et suivi sur mobile.
- Ne pas inventer de prix, délais, certifications ou caractéristiques produit.
- Séparer clairement faits validés, hypothèses et décisions en attente.
- Pour une tâche multi-couches, établir un plan et identifier les contrats affectés avant l'édition.
- Pour toute modification d'API, de domaine, de données ou d'exploitation, mettre à jour le document correspondant.

## Routage rapide

| Domaine | Documents principaux |
|---|---|
| Produit | `docs/PRODUCT.md`, `docs/DOMAIN.md` |
| Design et UX | `docs/DESIGN.md`, `docs/QA.md` |
| Frontend | `docs/FRONTEND.md`, `docs/API.md` |
| Backend | `docs/BACKEND.md`, `docs/DATA.md` |
| Tests et QA | `docs/TESTING.md`, `docs/QA.md` |
| Sécurité | `docs/SECURITY.md` |
| Déploiement | `docs/OPERATIONS.md` |
| Agents | `docs/AGENT-WORKFLOW.md` |
| Décisions | `docs/DECISIONS.md` |

## Definition of done globale

- Objectif et périmètre respectés.
- Tests proportionnés au risque exécutés.
- Erreurs, accessibilité, sécurité et exploitation évaluées.
- Documentation et décisions mises à jour.
- Aucun secret, donnée personnelle ou contenu non autorisé ajouté.
- État Git vérifié et fichiers étrangers préservés.
