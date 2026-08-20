# Contribuer à APOSA

## Avant de commencer

Lire `AGENTS.md` et la documentation de `docs/`. Les décisions structurantes doivent être consignées dans `docs/DECISIONS.md` avant de figer une technologie ou un comportement métier.

## Branches

Créer une branche courte depuis `main` :

- `feat/nom-court`
- `fix/nom-court`
- `docs/nom-court`
- `chore/nom-court`

## Commits

Utiliser des messages concis inspirés de Conventional Commits :

```text
feat: add edition preorder state
fix: prevent orders after preorder closure
docs: document sizing policy
chore: configure repository metadata
```

## Pull requests

- Expliquer le problème avant la solution.
- Garder une PR focalisée.
- Ajouter des captures pour les changements visuels.
- Vérifier mobile, accessibilité et états d'erreur.
- Mettre à jour la documentation avec le code.
- Ne jamais inclure de secret, donnée client ou affirmation commerciale non sourcée.

## Publication

Ne pas pousser directement sur `main`. Utiliser une pull request et privilégier un squash merge afin de conserver un historique lisible.
