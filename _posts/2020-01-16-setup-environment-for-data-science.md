---
layout: post
current: post
cover:  assets/images/post-setup-env.jpg
navigation: True
title: Setting up my environment for Data Science
date: 2020-01-16 10:00:00
tags: [dev]
class: post-template
subclass: 'post tag-dev'
author: ibarrond
---



Let's set up a dev environment from scratch! This quick guide will cover `Python` (and packages, including Jupyter Notebooks), `bash`, `git` and VSCode.

# 1. Python
Personally I use Python (over R) for most of my projects, due to the large amount of useful packages available. In order to install the Python Packages required for a Data Science build, one could use the generic Anaconda, or if you're like me and you hate downloading a lot of useless stuff and controlling your environment and installed packages, you can use the following list of packages by writing it into a `requirements.txt` file and running `pip install -r requirements.txt`.

```python
# Generic Math
numba
numpy
scipy
cython

# Notebooks
jupyter
jupytext
jupyter_contrib_nbextensions

# Data Science
dask
pandas
statsmodels
xgboost

# Data visualization
holoviews
datashader
matplotlib
matplotlib_venn
seaborn
bokeh

# Web App and REST
requests
flask

# Machine & Deep Learning
tensorflow
tensorflow_hub
tensorflow_datasets 
scikit-learn

# Time Series (Only in Linux)
# pystan 
# fbprophet
```

Alternatively, you can just download the [requirements.txt file](https://ibarrond.github.io/assets/files/requirements.txt).