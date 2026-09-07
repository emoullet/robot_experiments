# Expériences robotiques

Dépôt fédérateur personnel de préparation, sous **emoullet**. Chaque expérience
est un dépôt autonome référencé ici comme sous-module à un commit précis.
Les dépôts de l'organisation ISIR-EXTENDER ne sont pas modifiés par cette mise en place.

| Expérience | Dépôt | État |
| --- | --- | --- |
| Snake | [emoullet/exp_snake](https://github.com/emoullet/exp_snake) | Cadrage versionné et brouillon de bringup ; application non implémentée |

## Récupérer les expériences

```bash
git clone --recurse-submodules https://github.com/emoullet/robot_experiments.git
```

Le dépôt fédérateur est public ; certaines expériences et dépendances sont privées.
Le clonage récursif demande les droits GitHub correspondants. Cloner le dépôt
fédérateur sans récursion permet de consulter la méthode sans ces accès.

Après changement de version, dans une copie de travail propre :

```bash
git submodule update --init --recursive
```

Ne pas utiliser `--remote` pour reproduire une version : les commits enregistrés
dans les dépôts parents sont la référence. Publier les commits des dépendances,
puis ceux de l'expérience, puis la nouvelle référence dans ce dépôt fédérateur.
Chaque expérience doit être compilée dans un workspace distinct du développement
courant. `COLCON_IGNORE` empêche de découvrir accidentellement ces copies imbriquées.

## Méthode et décisions

- [Méthodologie de travail](docs/methodologie.md) : articulation Work, Drive, Codex et Git.
- [Décisions et état de reprise](docs/decisions.md) : choix retenus et travaux restants.
- Les détails scientifiques et opérationnels de Snake sont dans son dépôt privé.

Ce dépôt catalogue les versions des expériences. Le commit propre à une expérience
reste la référence principale pour identifier une session. Les données et les
registres d'identité sont conservés hors Git.
