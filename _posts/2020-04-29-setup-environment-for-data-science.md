---
layout: post
current: post
cover:  assets/images/post-setup-env.jpg
navigation: True
title: Setting up my environment for Data Science
date: 2020-04-29 10:00:00
tags: [dev]
class: post-template
subclass: 'post tag-dev'
author: ibarrond
---



Let's set up a Data Science dev environment from scratch! This quick guide will cover `Python` (and packages, including Jupyter Notebooks) and `bash`.

# 1. Python
Python ([download](https://www.python.org/downloads/)) is the language to go for most Data Science projects, due to the large amount of useful packages available. In order to install the Python Packages required for a Data Science build, one could use the generic Anaconda, or if you're like me and you hate downloading a lot of useless stuff and controlling your environment and installed packages, you can use a curated list of packages by running the following command

```bash
pip install -r https://ibarrond.github.io/assets/files/requirements.txt
```

These are the included packages: 

```python
# Generic Math
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
```

Alternatively, you can just download the [requirements.txt file](https://ibarrond.github.io/assets/files/requirements.txt) and install it via `pip install -r requirements.txt` .
## 1.1 Jupyter notebook extensions
The `jupyter_contrib_nbextensions` package requires some local setup (installing JS files and activating extensions). For this, run (copy-paste in a console and execute):

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
# 2. Bash
Flavouring my preferred terminal, Bash, is achieved using a `.bashrc` file. To use it, just download my [bashrc file](https://ibarrond.github.io/assets/files/.bashrc) and run it:
```bash
cd ~
curl -s https://ibarrond.github.io/assets/files/.bashrc
source .bashrc
```