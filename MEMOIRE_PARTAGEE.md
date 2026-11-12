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

## Validation du 12 novembre 2026

Yann a ajouté la permission workflow au jeton HTTPS, permettant le push du
commit `29c60ff` sur origin/beta. Les Actions du fork ont été activées, puis
le workflow Tests lancé manuellement sur beta. Ruff, Pyright et les deux
suites Home Assistant (2026.8.3 et 2025.12.0) ont réussi :
https://github.com/kangaroos4ever/cozytouch/actions/runs/43190751878
Aucune installation locale, release, promotion main, utilisation du compte
Cozytouch réel ni Pull Request vers upstream.

## Proposition à upstream — 12 novembre 2026

Source : demande suivante de Yann dans le même chat, autorisant la proposition
au projet d’origine. Elle remplace l’interdiction temporaire précédente.
PR ouverte : https://github.com/gduteil/cozytouch/pull/213
Branche du fork : `fix-cloud-recovery`, commit `6db1e8a`, créée depuis
upstream/main avec uniquement les correctifs, les tests et une note technique.
Code et tests identiques à la bêta validée ; 25 scénarios isolés revérifiés.
Les réglages de CI beta et documents propres au fork restent sur beta.
L’option d’accès en écriture et aux secrets pour les mainteneurs est décochée.
Aucune fusion, release, promotion main ni installation Home Assistant.
Statut : proposition ouverte, revue du mainteneur attendue.
