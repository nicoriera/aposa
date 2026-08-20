# APOSA — Workflow des agents

## Objectif

Donner aux agents le minimum de contexte nécessaire tout en imposant les contrôles adaptés au risque.

## Routage par tâche

| Tâche | Documents obligatoires |
|---|---|
| Produit ou métier | `PRODUCT.md`, `DOMAIN.md`, `DECISIONS.md` |
| UX ou design | précédents + `DESIGN.md`, `QA.md` |
| Frontend | `FRONTEND.md`, `API.md`, `DESIGN.md`, `TESTING.md` |
| Backend | `BACKEND.md`, `DOMAIN.md`, `API.md`, `DATA.md` |
| Paiement ou commande | précédents + `SECURITY.md`, `QA.md` |
| Données | `DATA.md`, `SECURITY.md`, `OPERATIONS.md` |
| QA ou tests | `QA.md`, `TESTING.md`, documents du domaine testé |
| Déploiement | `OPERATIONS.md`, `SECURITY.md`, `DECISIONS.md` |
| Documentation | `README.md`, documents liés et `AGENTS.md` |

## Cycle d'une tâche

1. **Lire** les instructions racine, le skill et les documents routés.
2. **Inspecter** le code et les décisions existantes avant de proposer.
3. **Cadrer** objectif, hors périmètre, hypothèses et risques.
4. **Planifier** lorsque plusieurs fichiers, couches ou validations sont concernés.
5. **Implémenter** le plus petit changement cohérent.
6. **Tester** selon le risque et les contrats touchés.
7. **Revoir** sécurité, accessibilité, données et exploitation.
8. **Documenter** toute décision durable ou contrat modifié.
9. **Rapporter** résultat, tests, limites et prochaine décision.

## Niveaux de risque

- **Faible** : texte, documentation, styles isolés ; vérification ciblée.
- **Moyen** : composant, endpoint non critique, contenu administrable ; tests unitaires et intégration pertinente.
- **Élevé** : paiement, commande, auth, données, clôture, migration ou production ; plan explicite, tests multi-couches, revue sécurité et procédure de retour arrière.

## Règles de délégation

- Déléguer uniquement un sous-problème borné et indépendant.
- Ne jamais déléguer la lecture ou l'interprétation des instructions du skill.
- Éviter que plusieurs agents modifient les mêmes fichiers.
- Fournir au sous-agent les artefacts, contraintes et résultat attendu, pas la conclusion.
- L'agent principal reste responsable de l'intégration et de la validation.

## Artefacts attendus

- Une décision structurante produit un ADR.
- Un changement d'API met à jour `API.md` et ses tests de contrat.
- Une règle métier met à jour `DOMAIN.md` et ses tests.
- Un composant réutilisable documente ses états et accessibilité.
- Un risque opérationnel nouveau produit ou met à jour un runbook.

## Interdictions

- Inventer une exigence ou une valeur commerciale.
- Modifier silencieusement un contrat.
- contourner une validation pour faire passer la CI ;
- mélanger refonte et correction ciblée sans accord ;
- ajouter une dépendance sans vérifier besoin, maintenance, licence et sécurité ;
- pousser ou publier sans autorisation correspondante.
