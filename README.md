# SCELYANS – feuilles des ADN 2026

**Ne faites pas confiance. Vérifiez.**

Ce dépôt public contient, pour chaque jour de 2026, la liste des **empreintes** (SHA-256) de toutes les feuilles qui composent l'ADN SCELYANS du jour. Il ne contient **aucun prix, aucun cours, aucune donnée de plateforme** : seulement des empreintes.

## À quoi ça sert

Chaque minute, SCELYANS relève les cours publics de plusieurs plateformes d'échange de cryptomonnaies et les inscrit dans un registre chaîné. Chaque ligne de ce registre est une **feuille**. Chaque jour, toutes les feuilles sont résumées en une seule empreinte, la **racine**, au cœur de l'**ADN du jour**. Cet ADN est publié et ancré dans la blockchain Bitcoin (OpenTimestamps).

Les fichiers de ce dépôt permettent à n'importe qui de **recalculer cette racine** à partir des feuilles, et donc de vérifier qu'aucune feuille n'a été ajoutée, retirée ou modifiée depuis le scellement.

## Contenu

- `feuilles-AAAA-MM-JJ.txt.gz` : une empreinte SHA-256 par ligne, dans l'ordre du registre, pour le jour indiqué. Environ 21 000 lignes par jour.
- Un fichier est ajouté une seule fois par jour. Il n'est **jamais modifié ni supprimé** : l'historique git en est la preuve.

## Comment vérifier

Il faut trois éléments publics :

1. le fichier de feuilles du jour, dans ce dépôt ;
2. l'ADN publié du même jour ;
3. l'empreinte quotidienne publiée dans le dépôt `trackyzz-empreintes`.

L'outil de vérification `verify.py`, publié dans le dépôt `scelyans-archive`, recalcule la racine à partir des feuilles et la compare à celle de l'ADN, puis contrôle l'ancrage Bitcoin. La méthode est décrite en détail dans le fichier `MERKLE.md` du même dépôt.

## Ce que ce dépôt prouve, et ce qu'il ne prouve pas

- **Il prouve** que l'ensemble des feuilles d'un jour n'a pas changé depuis son scellement.
- **Il ne prouve pas** à lui seul la justesse d'un cours : il prouve que le relevé n'a pas été modifié après coup.
- Les minutes manquantes ou en retard ne sont jamais comblées : elles sont signalées dans l'ADN du jour.

## Contact

contact@scelyans.com
