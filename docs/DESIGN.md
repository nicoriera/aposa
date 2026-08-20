# APOSA — Système de design

## Intention

Créer une expérience à la rencontre d'une galerie, d'un dossier technique et d'un atelier. Le design doit valoriser l'œuvre tout en rendant la précommande immédiatement compréhensible.

## Principes

1. **L'œuvre domine** : les visuels sont le contenu principal, pas une décoration.
2. **L'information rassure** : prix, taille, clôture et expédition ne sont jamais cachés.
3. **La grille structure** : alignements nets, espace généreux et hiérarchie stable.
4. **Le mouvement explique** : une animation révèle un état ou une relation ; elle ne bloque jamais.
5. **Chaque édition varie dans un système stable** : la couleur signal et les motifs changent, l'ergonomie reste constante.

## Direction visuelle initiale

- Base claire, noire et grise.
- Une couleur signal par édition.
- Typographie grotesque pour la lecture.
- Typographie monospace réservée aux métadonnées, références et statuts.
- Filets, repères, numéros et grilles inspirés des plans techniques.
- Angles droits ou rayons discrets.
- Pas d'ombres décoratives ni d'effets gratuits.

Les familles typographiques, couleurs exactes, échelles et tokens restent **à décider** après sélection d'une direction visuelle.

## Composants fondamentaux

- en-tête et navigation ;
- identité d'édition ;
- statut de précommande ;
- compte à rebours honnête basé sur la clôture réelle ;
- galerie média ;
- choix de produit et variante ;
- guide des tailles ;
- calendrier de fabrication ;
- journal de production ;
- récapitulatif panier ;
- messages d'erreur, confirmation et indisponibilité.

Chaque composant doit documenter : anatomie, variantes, états, comportement responsive, accessibilité et contenu attendu.

## Responsive

- Concevoir à partir de 320 px sans dépendre d'un appareil précis.
- Conserver l'action de précommande accessible sur petit écran.
- Éviter le scroll horizontal hors galeries explicitement annoncées.
- Adapter la densité, sans supprimer les informations contractuelles.
- Préserver une taille de texte et des cibles tactiles confortables.

## Mouvement

- Respecter `prefers-reduced-motion`.
- Limiter les animations aux transitions d'état, révélations de contenu et retours d'action.
- Ne jamais retarder le panier ou le paiement.
- Éviter les vidéos en lecture automatique avec son.

## Contenu et ton

- Court, factuel et précis pour le commerce.
- Plus éditorial pour le manifeste et l'œuvre.
- Ne jamais employer de pression artificielle.
- Distinguer faits, estimations et engagements.
- Employer « précommande » de façon constante.

## Validation design

Une direction n'est implémentable qu'après validation de :

- desktop et mobile ;
- page d'édition et fiche produit ;
- panier et paiement ;
- états teasing, ouvert, fermé, production et archive ;
- contraste, focus clavier et réduction du mouvement.
