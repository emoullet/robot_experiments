# Méthodologie de travail — décisions du 7 septembre 2026

## Finalité

Relier chaque résultat à ce qui a été évalué et à la manière de l'évaluer :
protocole, sources, exécutables, paramètres, setup, événements et données.

## Organisation

`robot_experiments` est un dépôt fédérateur. Chaque expérience possède son dépôt
autonome et référence par sous-modules les dépôts nécessaires. Une branche sert au
développement ; un commit fixe une version. Les dépendances imbriquées sont
également identifiées. Les versions doivent rester accessibles aux reproducteurs.

La préparation est effectuée sous le compte personnel emoullet. Une éventuelle
migration vers ISIR-EXTENDER fera l'objet d'une décision ultérieure.

## Work, Drive, Codex et Git

| Espace | Responsabilité |
| --- | --- |
| Work et Drive | Bibliographie, conception, discussion, rédaction collaborative et interprétation |
| Codex et dépôts locaux | Confrontation au code réel, faisabilité, implémentation et vérifications |
| Git de l'expérience | Versions applicables du protocole, outils, configurations et références des dépendances |
| Stockage local | Données brutes et manifestes ; copie vers Drive après clôture et vérification |

Les discussions peuvent se poursuivre dans les deux outils. Leur contexte partagé
est constitué de documents explicites, sans supposer une synchronisation des chats.
Un passage de relais indique les décisions, leurs raisons, les questions ouvertes,
les changements attendus et les éléments permettant de les vérifier. Le chercheur
arbitre les choix scientifiques.

Drive accueille les versions en discussion. Git conserve les versions applicables
aux acquisitions. Une modification du Drive ne change pas rétroactivement une
session. Une proposition générée dans Work n'est pas automatiquement une décision.

## Cycle de travail

1. Concevoir : hypothèses, conditions, tâches, mesures et analyse prévue.
2. Implémenter et piloter : instrumentation, interface, essais et ajustements tracés.
3. Identifier une version expérimentale : protocole, code, paramètres et setup.
4. Acquérir : enregistrer versions effectives, phases, essais et déviations.
5. Analyser : identifier données d'entrée, code et paramètres ; produire des résultats reproductibles.
6. Interpréter et rédiger avec des références aux résultats produits.

## Trois objets distincts

- Version expérimentale : définition prévue du protocole et du système.
- Session : déroulement réel d'un participant pseudonymisé avec cette version.
- Analyse : traitement identifié d'un ensemble de sessions, éventuellement réalisé plus tard.

Un commit ne capture ni les modifications locales ni la compilation effective.
Les manifestes doivent décrire l'environnement réellement utilisé. La stratégie de
preuve de compilation et d'archivage des changements locaux reste à implémenter.

## Usage et données

L'expérimentateur principal peut être aidé. Une application web locale doit lancer
et superviser la pile, guider les sessions et fournir l'analyse. Le démarrage
logiciel et l'autorisation de mouvement sont distincts. L'application fonctionne
indépendamment d'une conversation ou d'une connexion à Work/Codex.

Les données brutes sont conservées localement hors Git, avec identifiants uniques,
événements et signaux temporellement alignés. Les résultats dérivés sont régénérables.
Une interruption ne supprime jamais les acquisitions précédentes. Le registre
identité–pseudonyme reste séparé et n'est pas inclus dans les exports de partage.

Un workspace de compilation est dédié à chaque expérience. La mutualisation des
fonctions de supervision et de session sera étudiée à partir de Snake ; aucun
framework commun n'est imposé à ce stade.
