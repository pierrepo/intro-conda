---
title: TP Conda
author: Pierre Poulain
license: Creative Commons Attribution-ShareAlike (CC BY-SA 4.0)
---

# TP

## Installation de conda

### Sur les machines des salles informatiques à l'université

N'installez pas conda vous-même sur les machines des salles infos. Nous l'avons déjà fait pour vous. Vous avez accès à une version centralisée de conda.

Pour vérifier que conda est fonctionnel, utilisez la commande suivante :

```bash
conda --version
```

Vérifiez également que mamba est disponible :

```bash
mamba --version
```

Listez enfin les environnements déjà existants :

```bash
conda env list
```

### Sur votre propre machine (à la maison ou au labo)

⚠️ Uniquement si cela ne fonctionne pas sur les machines des salles informatiques !

Installez conda en suivant ces instructions :

<https://python.sdv.univ-paris-diderot.fr/annexe_install_python/>


## Virtuellement avec Binder

⚠️ Uniquement si cela ne fonctionne pas sur les machines des salles informatiques et sur votre propre machine !

Suivez le tutoriel [Introduction to Conda](https://astrobiomike.github.io/unix/conda-intro) du blog [Happy Belly Bioinformatics](https://astrobiomike.github.io/).

Vous pouvez le réaliser sur votre propre machine ou sur un serveur virtuel en cliquant sur le bouton « launch binder ».


## Exploration d'un environnement 

Créez l'environnement conda `rnaseq` à partir du fichier [rnaseq.yml](https://raw.githubusercontent.com/pierrepo/intro-conda/master/rnaseq.yml). Utilisez `mamba`.

Chargez ce nouvel environnement.

Quelle version a été installée pour les logiciels :

- fastqc ? (`fastqc --version`)
- samtools ? (`samtools --version`)

Quelles sont les dernières version disponibles dans conda ? (<https://anaconda.org/search>)


## Création de votre environnement pour le projet court

Essayez de créer un environnement conda pour votre projet court.

Pour cela :

1. Identifiez le langage de programmation que vous utiliserez.
2. Identifiez les bibliothèques associées dont vous aurez besoin.
3. Identifiez les autres logiciels dont vous aurez besoin.

Pour chacun de ces éléments, vérifiez s'il est disponible dans conda. Utilisez le moteur de recherche d'[anaconda.org](https://anaconda.org/search).

Que faire si ce n'est pas le cas ?

Créez un fichier `environment.yml` qui contient la description de votre environment (inspirez-vous de [rnaseq.yml](https://raw.githubusercontent.com/pierrepo/intro-conda/master/rnaseq.yml)), puis installez-le avec `mamba`. Conseil : dans un premier temps, ne préciser par les versions des outils que vous installez.

Chargez votre environnement et vérifiez que tous les langages, bibliothèques et logiciels dont vous avez besoin sont présents.

S'il manque des outils, modifiez le fichier `environment.yml` puis mettez à jour votre environnement avec la commmande :

```bash
mamba env update -f environment.yml
```

Vérifiez encore une fois que tous les outils dont vous avez besoin sont disponibles.

Déconnectez-vous de votre environnement. Vérfiez que les outils de votre projet ne sont plus disponibles. Chargez à nouveau notre environnement et vérifiez une dernière fois que tous les outils sont présents.

Déposez votre fichier `environment.yml` dans le dépôt GitHub de votre projet court.

Pensez enfin à **écrire une notice** (par exemple dans un fichier `README.md` comme [celui-ci](https://github.com/MDverse/mdws/) ou [celui-là](https://github.com/data-fun/3d-genome-builder)) décrivant la manière de construire votre environnement conda et si besoin, d'installer les logiciels tierces non disponibles dans conda.


