# État du fork Cozytouch — 12 novembre 2026

Base : `gduteil/cozytouch`, commit `63db34b`, version applicative `2026.10.0`.
Aucune nouvelle livraison ni version publiée ; aucun déploiement Home Assistant.

`origin` est le fork `kangaroos4ever/cozytouch`, `upstream` le projet d'origine.
Les worktrees locaux sont `cozytouch` sur main et `cozytouch-Beta` sur beta.
HTTPS et le Trousseau macOS assurent l'authentification Git.

Corrections beta : refus du mode Absence remonté à l'utilisateur, HTTP 429 sur
l'authentification et pause revérifiée sous verrou, réutilisation des jetons
valides après incident réseau, renouvellement après HTTP 401, validation des
réponses JSON sur les chemins de connexion, lecture et suivi d'exécution.
La CI se déclenche aussi sur les push beta.

Tests de régression : `tests/test_cloud_recovery.py`. Le Mac possède Python
3.9.6, sans l'environnement Home Assistant/Python 3.14.2 demandé par la suite.
Validation du code du commit `29c60ff` réussie sur GitHub Actions : Ruff,
Pyright et les deux suites Home Assistant 2026.8.3 / Python 3.14.2 et
Home Assistant 2025.12.0 / Python 3.13.7. Exécution :
https://github.com/kangaroos4ever/cozytouch/actions/runs/43190751878
Les 25 scénarios isolés locaux ont aussi réussi. Rien n’a été installé sur
le Mac ; cela ne prouve pas le fonctionnement sur le Kelud réel.

Les workflows du fork ont été activés ; les tests ont été déclenchés sur beta.
Le jeton HTTPS a reçu de Yann la permission workflow nécessaire au push.
Aucune release ni Pull Request vers upstream n’a été créée.

En attente : essais contrôlés dans Home Assistant après autorisation.
Aucune Pull Request vers upstream autorisée actuellement.
