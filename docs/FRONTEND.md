# APOSA — Architecture frontend

## Responsabilité

Le frontend présente l'état réel du domaine, collecte les choix du client et orchestre le parcours sans décider seul des règles commerciales.

## Principes

- Rendu rapide et progressif sur mobile.
- HTML sémantique avant abstraction de composants.
- État serveur comme source de vérité pour édition, prix, paiement et commande.
- État local limité aux interactions éphémères.
- Validation client pour aider ; validation serveur pour garantir.
- Aucune logique critique fondée uniquement sur l'horloge du navigateur.

## Découpage recommandé

```text
app / routes
features
  editions
  catalog
  cart
  checkout
  account
  production-tracking
components
  ui
  commerce
lib
  api
  validation
  analytics
  accessibility
styles / tokens
```

Adapter ces noms au framework retenu sans mélanger les responsabilités.

## Routes fonctionnelles

- `/` : redirection ou présentation de l'édition active.
- `/editions/:slug` : édition actuelle ou archivée.
- `/atelier` : manifeste et fabrication.
- `/cart` : panier.
- `/checkout` : étape de paiement si elle est hébergée par APOSA.
- `/order/:reference` : confirmation et suivi sécurisé.
- `/account/*` : espace facultatif.
- `/help/*` et pages légales.

Les routes finales seront confirmées avec la stack et la stratégie SEO.

## Gestion des états

- Représenter explicitement chargement, succès, vide, erreur et données périmées.
- Revalider prix, variante et disponibilité à l'ajout puis avant paiement.
- Après clôture, désactiver l'achat sur réponse autoritaire du serveur.
- Ne pas transformer un retour de paiement en confirmation sans vérification serveur.

## Performance

- Définir des budgets avant implémentation : poids initial, images, polices et JavaScript.
- Charger l'image adaptée au viewport et au DPR.
- Préférer les formats modernes avec repli pertinent.
- Réserver les dimensions des médias pour éviter les décalages.
- Charger les scripts tiers après consentement et seulement si nécessaires.

## Accessibilité

- Navigation complète au clavier.
- Focus visible et logique.
- Noms accessibles pour tous les contrôles.
- Erreurs liées aux champs et annoncées aux technologies d'assistance.
- Statuts de production compréhensibles sans couleur seule.
- Tests automatiques complétés par des vérifications manuelles.

## Analytics

Événements minimaux et non sensibles :

- vue d'édition ;
- consultation du guide des tailles ;
- sélection d'une variante ;
- ajout au panier ;
- début de paiement ;
- commande confirmée.

Ne jamais envoyer d'adresse, d'email, de nom ou de donnée de paiement dans les analytics.
