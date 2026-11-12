# Travail dans le fork Cozytouch de Yann

Les conventions communes du dossier Développements logiciels s'appliquent.
Lire aussi `CLAUDE.md`, `MEMORY.md`, `ETAT_PROJET.md` et `MEMOIRE_PARTAGEE.md`.

- `origin` : https://github.com/kangaroos4ever/cozytouch.git (fork de Yann).
- `upstream` : https://github.com/gduteil/cozytouch.git (projet d'origine).
- Développement dans `cozytouch-Beta`, branche `beta` ; `cozytouch` reste sur
  `main`. Préserver les changements locaux, récupérer origin avant travail,
  avancer uniquement par fast-forward, pousser chaque commit immédiatement.
- Ne pas ouvrir de Pull Request ni proposer les modifications à upstream pour
  le moment (demande de Yann du 12 novembre 2026). Ne pas promouvoir vers main
  sans validation explicite.
- Ne rien installer sur le Mac sans nouvelle autorisation. Les dépendances
  nécessaires aux tests peuvent être installées dans les runners GitHub Actions.
- Ne pas lire le jeton GitHub ni l'inscrire dans les fichiers ou commandes.
- Ne pas tester avec un compte Cozytouch réel. Utiliser les réponses simulées.
- Avant push, lancer `scripts/check.sh` si son environnement existe. En son
  absence, signaler la limite, vérifier ce qui est possible sans installation
  et suivre la CI du fork. Ne pas annoncer de validation Home Assistant réelle.
- Conserver les règles du projet d'origine pour les contributions futures ;
  ne pas déclencher de release, de tag ou de déploiement.
