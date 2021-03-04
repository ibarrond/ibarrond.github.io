---
layout: post
current: post
cover:  assets/images/post-setup-env.jpg
navigation: True
title: Setting up my environment
date: 2020-04-29 10:00:00
tags: [dev]
class: post-template
subclass: 'post tag-dev'
author: ibarrond
---



Let's set up a development environment from scratch! This guide will cover __Python__ (and packages, and Jupyter Notebooks), __C++__, __bash__ and __VSCode__ (lincluding _LaTEX_).

First things first: I code in _Python_ for most things not requiring performance (including almost all Data Science), and _C++_ or _Cython_ (a Python library with extensions in Jupyter Notebooks) for performance critical applications. I've gotten used to do most of my work on __VSCode__, but I still like using __Jupyter Notebooks__ for quick prototyping and visualization. Additionally, I write documents using LaTEX, the de-facto standard for scientific publications, integrated directly in VSCode. This setup is convenient both for Data Science and Cryptography.



# 1. Python
Python ([download](https://www.python.org/downloads/)) is the language to go for most Data Science projects, due to the large amount of useful packages available. In order to install the Python Packages required for a Data Science build, one could use the generic Anaconda, or if you're like me and you hate downloading a lot of useless stuff and keeping a 'minimalistic' list installed packages, you can use a curated list of packages by running the following command

```bash
pip install -r https://ibarrond.github.io/_includes/files/requirements.txt
```

These are the included packages: 

```python
{% include files/requirements.txt %}
```

Alternatively, you can just download the [requirements.txt file](https://ibarrond.github.io/_includes/files/requirements.txt) and install it via `pip install -r requirements.txt`.
## 1.1 Jupyter notebook extensions
The `jupyter_contrib_nbextensions` package requires some local setup (installing JS files and activating extensions). For this, run (copy-paste in an elevated console and execute):

```bash
wget -O jupyter_extensions.ps1 https://ibarrond.github.io/_includes/files/jupyter_extensions.txt
. jupyter_extensions.ps1
```

This will install the following extensions:

```bash
{% include files/jupyter_extensions.txt %}
```

# 1.2 Jupyter Notebook header
To add a bit of style to the header of a notebook, I always include this title (in a markdown cell) and a text abstract (also found [here](https://ibarrond.github.io/_includes/files/title.html)):
```html
{% include files/title.html %}
```

# 2. Bash
Flavouring my preferred terminal, Bash (in Linux and WSL), is achieved using a `.bashrc` file. To use it, just download my [bashrc file](https://ibarrond.github.io/_includes/files/.bashrc) and run it:
```bash
wget -O ~/.bashrc https://ibarrond.github.io/_includes/files/bashrc.txt
. ~/.bashrc
```

# 3. VS Code
Download the installer from [here](https://code.visualstudio.com/docs/setup/setup-overview), install and run the following to install the extensions:

```bash
wget -O VS_Code_extensions.ps1 https://ibarrond.github.io/_includes/files/VS_Code_extensions.txt
. VS_Code_extensions.ps1
```

This will execute the following code:

```bash
{% include files/VS_Code_extensions.txt %}
```

# 4. LaTEX
There are multiple ways to get a working LaTEX distribution. My preferred is TEXLive, which downloads locally a very fat installer (4GB) and installs all the packages you need. Just go [here](https://www.tug.org/texlive/acquire-iso.html), download the big `.iso` file, mount it and install locally (it takes more than 1h to install). The LaTEX extension in VSCode should recognize it.

Additionally, I have a compilation of libraries and useful stuff in [here](https://ibarrond.github.io/_includes/files/ibarrondTEXCorner.tex), which can be obtained by running:

```bash
wget -O ibarrondTEXCorner.tex https://ibarrond.github.io/_includes/files/ibarrondTEXCorner.tex
```
Just add it at the top of your main latex document with `\include{ibarrondTEXCorner.tex}`.

