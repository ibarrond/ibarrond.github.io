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
pip install -r https://ibarrond.github.io/assets/files/requirements.txt
```

These are the included packages: 

```python
 Generic Math
numba    # Efficient NumPy JIT compiler
numpy    # Basic - Array computing
scipy    # More maths/engineering/scientific computing
cython   # Bridge C & C++ with Python

# Notebooks
jupyter  # Basic - Interactive notebooks
jupytext # Git meets Jupyter notebooks 
jupyter_contrib_nbextensions # Extensions for notebooks. Need config!

# Data Science
pandas   # Basic - Data processing, tables and dataframes
dask     # Scaling Numpy, Pandas, Scikit-Learn and XGBoost
statsmodels # Statistical models
xgboost  # State of the art decission trees

# Data visualization
matplotlib # Basic - plot data
holoviews  # Interactive data visualization
datashader # Render huge datasets
matplotlib_venn # Plotting Venn diagrams
seaborn    # Improving Matplotlib
bokeh      # Interactive data visualization

# Web App and REST
requests   # Basic - interact with any REST API
flask      # Web dev, lightweight compared to django

# Machine & Deep Learning
tensorflow           # Basic - Deep Learning from google
tensorflow_hub       # Collection of tf models
tensorflow_datasets  # Collection of tf datasets
scikit-learn         # Basic - Machine Learning

# Time Series (Only in Linux)
#   -> Requires a C++ compiler: sudo apt-get install build-essential
pystan;    platform_system!='Windows'
fbprophet; platform_system!='Windows'

# Utilities
pylint     # Better coding inside VSCode
```

Alternatively, you can just download the [requirements.txt file](https://ibarrond.github.io/assets/files/requirements.txt) and install it via `pip install -r requirements.txt`.
## 1.1 Jupyter notebook extensions
The `jupyter_contrib_nbextensions` package requires some local setup (installing JS files and activating extensions). For this, run (copy-paste in an elevated console and execute):

```bash
wget -O jupyter_extensions.ps1 https://ibarrond.github.io/assets/files/jupyter_extensions.txt
. jupyter_extensions.ps1
```

This will install the following extensions:

```bash
jupyter contrib nbextension install --system

# One-click pretty code
jupyter nbextension enable code_prettify/code_prettify
# Alt-C toggles code comment
jupyter nbextension enable comment-uncomment/main
# Show esecution time on code cells
jupyter nbextension enable execute_time/ExecuteTime
# hide code, useful to build app-like notebooks
jupyter nbextension enable hide_input_all/main
# Define initialization cells, run automatically at startup
jupyter nbextension enable init_cell/main
# Add jupytext
jupyter nbextension enable jupytext/index
# 80 chars per line of code!
jupyter nbextension enable ruler/main
# Try code in a quick-and-dirty way witn Ctrl-B
jupyter nbextension enable scratchpad/main
# Spellchecking, no more typos
jupyter nbextension enable spellchecker/main
# Two-column cells
jupyter nbextension enable splitcell/splitcell
# Automatic Table of contents
jupyter nbextension enable toc2/main
# Those beautiful pandas tables
jupyter nbextension enable table_beautifier/main
# List of variables
jupyter nbextension enable varInspector/main
# Remove navbar, useful with hide input for app-like notebooks
jupyter nbextension enable zenmode/main
```

# 1.2 Jupyter Notebook header
To add a bit of style to the header of a notebook, I always include this title (in a markdown cell) and a text abstract (also found [here](https://ibarrond.github.io/assets/files/title.html)):
```html
  <div style="font-variant: small-caps; font-weight: normal; font-size: 30px;  
              padding: 15px;            text-align: center;  margin: 10px;">
  This is a cool title
  </div> 

  <div style="font-variant: small-caps; font-weight: normal; font-size: 20px; 
              text-align: center;       padding: 15px;">
  and this is a subtitle
  </div> 

  <div style=" float:right;  font-size: 12px; line-height: 12px; padding: 10px 15px 8px;">
  Alberto IBARRONDO (Author)
  </div> 

  <div style=" display: inline-block; font-family: 'Lato', sans-serif; font-size: 12px;
      font-weight: bold; line-height: 12px; letter-spacing: 1px; padding: 10px 15px 8px;">
  09/10/2018 (date)
  </div>
```

# 2. Bash
Flavouring my preferred terminal, Bash (in Linux and WSL), is achieved using a `.bashrc` file. To use it, just download my [bashrc file](https://ibarrond.github.io/assets/files/.bashrc) and run it:
```bash
wget -O ~/.bashrc https://ibarrond.github.io/assets/files/bashrc.txt
. ~/.bashrc
```

# 3. VS Code
Download the installer from [here](https://code.visualstudio.com/docs/setup/setup-overview), install and run the following to install the extensions:

```bash
wget -O VS_Code_extensions.ps1 https://ibarrond.github.io/assets/files/VS_Code_extensions.txt
. VS_Code_extensions.ps1
```

This will execute the following code:

```bash
code --install-extension anseki.vscode-color --force
code --install-extension CoenraadS.bracket-pair-colorizer --force
code --install-extension eamodio.gitlens --force
code --install-extension esbenp.prettier-vscode --force
code --install-extension ginfuru.ginfuru-vscode-jekyll-syntax --force
code --install-extension James-Yu.latex-workshop --force
code --install-extension moshfeu.compare-folders --force
code --install-extension ms-python.python --force
code --install-extension ms-vscode-remote.remote-containers --force
code --install-extension ms-vscode-remote.remote-ssh --force
code --install-extension ms-vscode-remote.remote-ssh-edit --force
code --install-extension ms-vscode-remote.remote-wsl --force
code --install-extension ms-vscode-remote.vscode-remote-extensionpack --force
code --install-extension ms-vscode.cpptools --force
code --install-extension tcwalther.cython --force
code --install-extension VisualStudioExptTeam.vscodeintellicode --force
```

# 4. LaTEX
There are multiple ways to get a working LaTEX distribution. My preferred is TEXLive, which downloads locally a very fat installer (4GB) and installs all the packages you need. Just go [here](https://www.tug.org/texlive/acquire-iso.html), download the big `.iso` file, mount it and install locally (it takes more than 1h to install). The LaTEX extension in VSCode should recognize it.

Additionally, I have a compilation of libraries and useful stuff in [here](https://ibarrond.github.io/assets/files/ibarrondTEXCorner.tex), which can be obtained by running:

```bash
wget -O ibarrondTEXCorner.tex https://ibarrond.github.io/assets/files/ibarrondTEXCorner.tex
```
Just add it at the top of your main latex document with `\include{ibarrondTEXCorner.tex}`.