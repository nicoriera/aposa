# APOSA — Documentation du projet

Cette documentation constitue la source de vérité du projet. Le code, les tickets et les agents doivent s'y conformer.

## Parcours de lecture

### Comprendre le produit

1. [Vision produit](PRODUCT.md)
2. [Domaine et règles métier](DOMAIN.md)
3. [Architecture fonctionnelle](ARCHITECTURE.md)
4. [Glossaire](GLOSSARY.md)

### Concevoir l'expérience

1. [Direction produit et UX](PRODUCT.md)
2. [Système de design](DESIGN.md)
3. [Architecture frontend](FRONTEND.md)
4. [Accessibilité et QA](QA.md)

### Implémenter la plateforme

1. [Principes d'implémentation](IMPLEMENTATION.md)
2. [Architecture backend](BACKEND.md)
3. [Contrats API](API.md)
4. [Données](DATA.md)
5. [Tests](TESTING.md)
6. [Sécurité](SECURITY.md)
7. [Exploitation](OPERATIONS.md)
8. [Roadmap](ROADMAP.md)

### Travailler avec les agents

1. [Instructions racine](../AGENTS.md)
2. [Workflow des agents](AGENT-WORKFLOW.md)
3. [Journal des décisions](DECISIONS.md)
4. [Skill APOSA](../.agents/skills/aposa-project/SKILL.md)

## Autorité des documents

En cas de conflit, appliquer cet ordre :

1. exigences légales et sécurité ;
2. décisions acceptées dans `DECISIONS.md` ;
3. règles métier de `DOMAIN.md` ;
4. architecture et contrats ;
5. conventions d'implémentation ;
6. préférences locales d'un ticket.

Une décision nouvelle qui contredit un document existant doit mettre à jour les deux dans la même pull request.

## Statuts

- **Validé** : décision exploitable par le code.
- **Hypothèse** : direction de travail à tester.
- **À décider** : ne pas figer dans l'implémentation.
- **Déprécié** : conservé pour historique, ne plus appliquer.
