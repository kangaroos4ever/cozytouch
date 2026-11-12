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
La CI doit aussi se déclencher sur les push beta.

Tests de régression : `tests/test_cloud_recovery.py`. Le Mac possède Python
3.9.6, sans l'environnement Home Assistant/Python 3.14.2 demandé par la suite.
La validation complète doit donc être constatée sur GitHub Actions ; les
vérifications locales isolées ne prouvent pas le fonctionnement sur le Kelud.
Les résultats effectifs de cette intervention sont rapportés dans le chat.

En attente : validation CI du commit, puis essais contrôlés dans Home Assistant
après autorisation. Aucune Pull Request vers upstream autorisée actuellement.
