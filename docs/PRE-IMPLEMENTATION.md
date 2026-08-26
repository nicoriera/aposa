# APOSA — Check-list avant implémentation

Ce document fixe ce qui doit être **validé** avant d'ouvrir la Phase 2 (fondations applicatives) de la [roadmap](ROADMAP.md). Tant qu'un item bloquant reste ouvert, ne pas figer de stack ni démarrer le code métier.

Légende des cases :

- `[x]` déjà couvert par la documentation actuelle
- `[ ]` à faire ou à décider avant le code
- **Bloquant** : empêche le démarrage propre de l'implémentation
- **Souhaitable** : peut avancer en parallèle des fondations, mais doit être tranché avant le parcours public / commerce

Statuts à reporter dans `DECISIONS.md` : Validé | Hypothèse | À décider.

---

## 0. Prérequis documentaires (déjà en place)

- [x] Vision produit et modèle de précommande (`PRODUCT.md`, ADR-001)
- [x] Cycle d'édition et invariants (`DOMAIN.md`)
- [x] Architecture fonctionnelle et modules (`ARCHITECTURE.md`)
- [x] Règles d'implémentation, API, données, tests, sécurité, exploitation
- [x] Direction design initiale (principes, pas encore tokens)
- [x] Workflow agents et contribution

**Sortie** : cadre exploitable. Ne remplace pas les validations produit et techniques ci-dessous.

---

## 1. Produit — Drop 01 (Phase 0)

### 1.1 Textile et fabrication — **Bloquant**

- [ ] Choisir la référence Stanley/Stella définitive (ADR-002 encore « sous réserve »)
- [ ] Valider coloris, tailles ouvertes et tableau de mesures
- [ ] Prototyper, presser et contrôler un échantillon physique
- [ ] Documenter grammage, coupe, matières et limites après transformation
- [ ] Attribuer chaque certification / engagement à sa source exacte (référence + preuve)

### 1.2 Offre commerciale — **Bloquant**

- [ ] Définir le contenu exact du colis (vêtement, packaging, objets inclus ou non)
- [ ] Calculer coûts unitaires (textile, transfert, pressage, emballage, port)
- [ ] Fixer prix de vente TTC / HT, devise et marge technique minimale
- [ ] Définir le délai d'expédition estimé affiché avant paiement
- [ ] Décider fenêtre de précommande (dates, fuseau, clôture manuelle vs automatique)
- [ ] Décider s'il existe un plafond de quantité réel (sinon : rareté = temps uniquement)

### 1.3 Politiques client — **Bloquant**

- [ ] Rédiger et valider : précommande, livraison, retours / échanges, SAV
- [ ] Clarifier ce qui reste dû en cas d'annulation selon l'étape (avant / après gel d'approvisionnement)
- [ ] Préparer mentions légales, CGV, confidentialité et mentions d'accessibilité (brouillon juridique)

### 1.4 Identité et contenus Drop 01 — **Bloquant** pour le parcours public

- [ ] Œuvre / graphisme final (recto, verso, déclinaisons)
- [ ] Textes : manifeste, histoire, matières, fabrication, FAQ
- [ ] Médias : photos produit, détails, packaging (formats bruts prêts à optimiser)
- [ ] Guide des tailles avec mesures réelles du prototype
- [ ] Calendrier de fabrication (étapes et libellés, estimations vs faits)

**Sortie Phase 0** : fiche Drop 01 validée + prototype contrôlé. Sans elle, le catalogue et le checkout inventeraient des données.

---

## 2. Décisions techniques (Phase 1)

### 2.1 Stack et hébergement — **Bloquant**

- [ ] Choisir entre solution e-commerce adaptée vs application sur mesure (ADR)
- [ ] Framework / langage frontend et backend (ou plateforme)
- [ ] Base de données et stratégie de migrations
- [ ] Hébergement, environnements (local, preview, staging, production)
- [ ] CI : lint, types, tests, preview, secrets

### 2.2 Prestataires — **Bloquant** pour le commerce ; **souhaitable** pour les fondations

| Domaine | Décision ADR | Notes |
|---|---|---|
| Paiement | [ ] | Saisie carte déléguée ; webhooks signés |
| Emails transactionnels | [ ] | Confirmation, production, expédition |
| Livraison / transporteur | [ ] | Étiquettes, suivi, webhooks |
| CMS / contenus | [ ] | Ou contenus versionnés dans le dépôt |
| Médias (CDN / transformation) | [ ] | Budgets image avant code |
| Analytics + consentement | [ ] | Événements minimaux, hors données perso |
| Auth admin (MFA) | [ ] | Compte client facultatif déjà tranché |

### 2.3 Budgets et niveaux de service — **Souhaitable** avant Phase 3

- [ ] Budgets performance : poids initial, images, polices, JS (`FRONTEND.md`)
- [ ] Objectifs disponibilité pendant la fenêtre de précommande
- [ ] Estimation des coûts d'infra / prestataires pour un Drop
- [ ] RPO / RTO et politique de sauvegarde (ébauche)

### 2.4 Modèle de données exécutable — **Bloquant**

- [ ] Schéma logique des entités Edition / Product / Variant / Order (au-delà du conceptuel)
- [ ] Instantanés contractuels obligatoires sur les lignes de commande
- [ ] Stratégie d'identifiants publics (opaques, non séquentiels)
- [ ] Matrice de rétention (même brouillon) pour commandes, logs, paniers, consentements

**Sortie Phase 1** : architecture exécutable, aucun choix critique implicite. Chaque choix structurant a un ADR dans `DECISIONS.md`.

---

## 3. Design système — avant UI production

### 3.1 Direction visuelle — **Bloquant** pour les composants

- [ ] Valider la direction visuelle (desktop + mobile)
- [ ] Choisir familles typographiques (grotesque lecture + mono métadonnées)
- [ ] Définir tokens : couleurs de base, couleur signal Drop 01, échelles type / espace
- [ ] Maquettes ou wireframes haute fidélité des états d'édition :
  - teasing
  - précommande ouverte
  - fermée / sourcing / production / fulfilment
  - archive

### 3.2 Parcours critiques — **Bloquant** avant Phase 3–4

- [ ] Page édition + fiche produit
- [ ] Guide des tailles
- [ ] Panier et checkout (précommande, clôture, expédition visibles)
- [ ] Confirmation et suivi commande
- [ ] Contraste, focus clavier, `prefers-reduced-motion` validés sur ces écrans

Ne pas implémenter de tokens inventés : `DESIGN.md` les laisse explicitement **à décider**.

---

## 4. Go / no-go pour démarrer le code

### Autoriser la Phase 2 (fondations) si

1. Stack, hébergement, CI et secrets sont décidés (ADR acceptés).
2. Modèle de données et transitions d'édition sont prêts à être codés sans invention.
3. Aucune certification ou prix n'est requis dans le code fondation (stubs / fixtures synthétiques OK).
4. Les politiques précommande / retours ont au moins un brouillon validé métier (pas forcément juridique final).

### Reporter le parcours public (Phase 3) si

- Fiche Drop 01, médias, tailles ou textes manquent.
- Tokens design non validés.
- Mentions contractuelles essentielles absentes.

### Reporter le commerce (Phase 4) si

- Prestataire paiement / emails non choisi.
- Prix, taxes, délais d'expédition non figés.
- Politique d'annulation / remboursement non tranchée par étape.

---

## 5. Ordre de travail recommandé

```text
1. Fiche Drop 01 (textile, prix, délais, colis, politiques)
2. ADR stack + paiement + emails + hébergement
3. Direction visuelle + tokens + maquettes des états
4. Schéma données + budgets perf
5. Puis seulement : Phase 2 — initialisation repo applicatif
```

Les items 1–3 peuvent avancer en parallèle tant que les responsables métier / design / technique restent synchronisés via `DECISIONS.md`.

---

## 6. Ce qu'il ne faut pas faire avant ces validations

- Inventer prix, délais, certifications ou caractéristiques produit dans le code ou les fixtures « réalistes ».
- Simuler un stock ou un compteur de rareté faux.
- Figer un framework ou un prestataire sans ADR.
- Construire le checkout avant la clarté précommande / clôture / expédition.
- Copier des données personnelles réelles dans des environnements de test.

---

## Références

- [Roadmap](ROADMAP.md) — phases 0 à 7
- [Décisions](DECISIONS.md) — journal ADR
- [Produit](PRODUCT.md) · [Domaine](DOMAIN.md) · [Design](DESIGN.md)
- [Implémentation](IMPLEMENTATION.md) · [Architecture](ARCHITECTURE.md)
- Check-lists agents : `.agents/skills/aposa-project/references/product-checklist.md`, `engineering-checklist.md`
