class: center, middle

# Introduction à Conda

## M2BI 2019-2020


<br /><br /><br /><br /><br /><br />

.leftcol[
<img src="img/Universite_Paris_logo_horizontal_2000px.png"
	 height="100px" style="vertical-align:top;">
 </img>
]

.righcol.right[
<br /><br />
Pierre Poulain <br />
pierre.poulain@univ-paris-diderot.fr <br />
@pierrepo
]

.footer[
Ce contenu est mis à disposition selon les termes de la licence Creative Commons BY-SA 4.0
]

---

layout: true
name: title
class: center, middle
.footer[
Poulain 2019 CC BY-SA
]

---

layout: true
name: contentleft
class: top, left
.footer[
Poulain 2019 CC BY-SA
]

---

layout: true
name: contentcenter
class: top, center
.footer[
Poulain 2019 CC BY-SA
]

---

template: contentleft

# Objectifs d'apprentissage

--

- Décrire et expliquer l'organisation de l'écosytème conda.

- Utiliser et créer un environnement conda.

- Dupliquer un environnement conda.

---
template: contentleft

# XXXconda 🐍

[Anaconda](https://www.anaconda.com/)
- Distribution open source.
- Disponible pour Windows, Mac et Linux.
- Installable sans être **administrateur**.
- Nombreux outils pour l'analyse de données (en Python).

--

[Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- Version *light* d'Anaconda (le strict minimum).
- Aussi installable sans être **administrateur**.

--

[Conda](https://docs.conda.io/projects/conda/en/latest/index.html) ([Cheat sheet](https://docs.conda.io/projects/conda/en/latest/_downloads/1f5ecf5a87b1c1a8aaf5a7ab8a7a0ff7/conda-cheatsheet.pdf))
- Gestionnaire de logiciels installé avec Anaconda et Miniconda.
- Basé sur Python.

--

[Bioconda](https://bioconda.github.io/)
- Canal de diffusion de logiciels utilisés en bioinformatique.
- Utilisable par le gestionnaire de paquets conda.


---
template: contentleft

# L'écosystème Conda 🐍

.center[
<img height="400px" src="img/conda.png">
]


---
template: contentleft

# Installer Miniconda (au labo, à la maison)

<https://docs.conda.io/en/latest/miniconda.html>

- Miniconda > Anaconda (plus léger)
- Miniconda**3**

<br /><br />

Notice : <https://python.sdv.univ-paris-diderot.fr/annexe_install_python/> 👍

---
template: contentleft

# Utiliser Miniconda (au labo, à la maison)

.leftcol[
### Créer un environnement 
```
$ conda create -n test-end
```

### Charger un environnement 
```
$ conda activate test-env
```
🔍 Le prompt est modifié

]
--

.rightcol[
### Installer un logiciel
```
$ pip install numpy
```
ou
```
$ conda install jupyterlab
$ conda install -c bioconda samtools
```
⚠ Pas besoin d'être administrateur 

### Quitter un environnement
```
$ conda deactivate
```
]


---
template: contentleft

# Utiliser Miniconda (au labo, à la maison) (2)

.leftcol[
### Décrire l'environnement dans un fichier yaml (rnaseq.yml)

```
name: rnaseq-test
channels:
    - defaults
    - bioconda
    - conda-forge
dependencies:
    - fastqc
    - bowtie2
    - htseq
    - samtools=1.9
```
]

.rightcol[
### Créer un environnement
```
$ conda env create -f rnaseq.yml
```

### Supprimer un environnement
```
$ conda env remove -n rnaseq-test
```
]


---
template: contentleft

# Gérer les environnements

### Lister les environnements disponibles
```
$ conda env list
```

### Lister les logiciels installés dans un environnement (et leurs versions)
```
$ conda list -n ENVNAME
```

### Exporter un environnement dans un fichier yaml
```
$ conda env export -n ENVNAME > envname.yml
```

sans la localisation exacte :
```
$ conda env export -n ENVNAME | grep -v "^prefix:" > envname.yml
```

puis, ailleurs, plus tard :
```
$ conda env create -f envname.yml
```

---
template: contentleft

# Utiliser Miniconda (dans les salles infos)

Miniconda est déjà installé. **Ne l'installer pas dans vos sessions utilisateurs !**

--

Pour utiliser les environnements des profs :
```
$ conda env list
$ conda activate ENVNAME
$ ...
$ conda deactivate
```


---
template: contentleft

# Utiliser Miniconda (dans les salles infos) (2)

### Installer VOTRE environnement 
```
$ conda env create -f envname.yml -p /path/to/env/
```

Exemple :
```
$ conda env create -f rnaseq.yml -p ~/scratch/rnaseq-env/
```

--
### Charger VOTRE environnement 
```
$ conda activate /path/to/env/
```

Exemple :
```
$ conda activate ~/scratch/rnaseq-env/
```

---
template: contentleft

# Utiliser Miniconda (dans les salles infos) (3)

### Quitter VOTRE environnement
```
$ conda deactivate
```

--
### Supprimer VOTRE environnement
```
$ conda env remove -p /path/to/env/
```
Exemple :
```
$ conda env create -f rnaseq.yml -p ~/scratch/rnaseq-env/
```


---

template: contentleft

background-color: #cccccc

# C'est parti ! 🚀

## 💻 [Tutoriel](https://omics-school.github.io/analyse-rna-seq/analyse_RNA-seq_O_tauri.html)

