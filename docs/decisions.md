# Décisions et état de reprise

Décisions retenues le 7 septembre 2026 :

- Dépôt fédérateur et dépôts indépendants d'expériences, reliés par sous-modules.
- Dépendances de chaque expérience fixées par commits, sous-modules récursifs inclus.
- Mise en place personnelle sous emoullet ; pas de modification dans ISIR-EXTENDER.
- Discussion collaborative sur Drive, protocole applicable versionné dans Git.
- Interface web locale qui lance toute la pile, supervise et conduit les sessions.
- Stockage local hors Git, partage possible sur Drive après clôture.
- Identités conservées dans un registre séparé des données expérimentales.

## État

Structure de dépôts et documentation initiale. Les décisions spécifiques à Snake,
les paramètres retenus et les questions ouvertes sont dans `snake/protocol/` et
`snake/docs/etat_du_travail.md`. L'interface, le superviseur, l'acquisition et
l'analyse restent à développer. Aucune version n'est déclarée validée sur robot.

Les noms `exp_snake` et `dependencies/` sont des conventions initiales de structure.
Le dépôt Snake est privé ; la visibilité publique existante du fédérateur est conservée.

## Prochaine étape

Résoudre les points techniques du dépôt Snake, puis réaliser une chaîne minimale
en simulation : participant fictif, session, essai, acquisition, bilan et graphique.
La migration organisationnelle et la publication scientifique ne font pas partie
de cette mise en place.
