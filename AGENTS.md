# APOSA — Instructions for agents

## Mission

Construire APOSA comme un atelier lorientais d'éditions graphiques premium vendues en précommande, sans stock commercial permanent.

Avant toute modification produit ou technique, lire `docs/PRODUCT.md`, `docs/DOMAIN.md`, `docs/ARCHITECTURE.md` et `docs/IMPLEMENTATION.md`. Utiliser `.agents/skills/aposa-project/SKILL.md` pour toute tâche concernant APOSA.

## Principes non négociables

- Une édition est vendue pendant une fenêtre définie, puis produite après sa clôture.
- Ne jamais simuler une rareté par un faux stock ou un faux compteur.
- Afficher avant paiement le caractère de précommande, la clôture et le délai d'expédition.
- La commande doit rester accessible et prioritaire sur les effets graphiques.
- Concevoir mobile-first, avec une interface minimale, graphique et performante.
- Attribuer chaque certification et engagement à sa source exacte.
- Ne pas supposer qu'une fabrication après commande supprime les droits du consommateur.
- Ne pas figer une stack ou un prestataire sans décision documentée.

## Méthode

- Consigner les décisions durables dans `docs/DECISIONS.md`.
- Mettre à jour la documentation avec le code lorsque le domaine ou l'architecture change.
- Placer les règles métier dans le domaine, pas uniquement dans l'interface.
- Tester en priorité produit, taille, panier, paiement, confirmation et suivi sur mobile.
- Ne pas inventer de prix, délais, certifications ou caractéristiques produit.
