---
title: TP Conda
author: Pierre Poulain
license: Creative Commons Attribution-ShareAlike (CC BY-SA 4.0)
---

# TP

## Installation de conda

### Sur les machines des salles informatiques

Nous l'avons déjà fait pour vous. Vous avez accès à une version centralisée de conda.

N'installez pas conda vous-même sur les machines des salles infos.

Pour vérifier que conda est bien fonctionnelle, utilisez la commande suivante :

```bash
conda --version
```

Vérifiez également que mamba est disponible :

```bash
mamba --version
```

### Sur votre propre machine (à la maison ou au labo)

Installez conda en suivant ces instructions :

<https://python.sdv.univ-paris-diderot.fr/annexe_install_python/>


## Virtuellement avec Binder

Suivez le tutoriel [Introduction to Conda](https://astrobiomike.github.io/unix/conda-intro) du blog [Happy Belly Bioinformatics](https://astrobiomike.github.io/).

Vous pouvez le réaliser sur votre propre machine ou sur un serveur virtuel en cliquant sur le bouton « launch binder ».


## Exploration d'un environnement 

Créez l'environnement conda `rnaseq` à partir du fichier [rnaseq.yml](rnaseq.yml)

Quelle version a été installée pour les logiciels :

- fastqc ?
- samtools ?

Quelles sont les dernières version disponibles dans conda ?


## Création de votre environnement

Essayez de créer un environnement conda pour votre projet court.

Pour cela :

1. Identifiez le langage de programmation que vous utiliserez.
2. Identifiez les bibliothèques associées dont vous aurez besoin.
3. Identifiez les autres logiciels dont vous aurez besoin.

Pour chacun de ces éléments, vérifiez s'il est disponible dans conda. Utilisez le moteur de recherche d'[anaconda.org](https://anaconda.org/search).

Que faire si ce n'est pas le cas ?

Créez ensuite votre environnement puis installez les paquets un par un, en précisant si besoin les *channels* nécessaires.

Quand l'environnement vous semble fonctionel, créez un fichier `environment.yml` qui contient la description de votre environment.

Pensez enfin à écrire une notice décrivant la manière de construire votre environnement conda et si besoin, d'installer les logiciels tierces non compatibles avec conda.


