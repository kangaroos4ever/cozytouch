# Mémoire du fork Cozytouch

## 12 novembre 2026 — décisions confirmées de Yann

Source : chat « Rattacher Cozy Touch Atlantique à GitHub ».

- Équipement concerné : sèche-serviettes Sauter Kelud Wi-Fi sans passerelle.
- Fork créé sous `kangaroos4ever/cozytouch`, développement sur beta.
- Authentification Git HTTPS par jeton conservé dans le Trousseau ; aucune
  installation de GitHub CLI ou de Homebrew souhaitée.
- Autorisé : corriger les problèmes relevés par l'audit et pousser dans beta.
- Non autorisé pour le moment : proposer les changements au projet d'origine,
  ouvrir une Pull Request, promouvoir main ou déployer dans Home Assistant.
- Reporté : étude d'un pilotage local du Kelud. Aucune API locale confirmée ;
  le code du client cloud ne prouve pas qu'un service local existe.

## Audit et corrections

Les scénarios isolés de l'audit ont reproduit un succès apparent du mode
Absence après False, une absence de pause sur HTTP 429 d'authentification,
des connexions en attente ignorant une pause nouvellement armée, une nouvelle
authentification après timeout avec jeton valide et des exceptions JSON non
maîtrisées. Les changements sont expliqués dans `docs/decisions.md`, section
« Fork beta: recovery from cloud failures » ; tests dans
`tests/test_cloud_recovery.py`. Aucun compte Cozytouch réel n'a été utilisé.
