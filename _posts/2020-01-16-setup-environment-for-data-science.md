---
layout: post
current: post
cover:  assets/images/post-setup-env.jpg
navigation: True
title: Setting up an environment for Data Science
date: 2020-01-16 10:00:00
tags: [dev]
class: post-template
subclass: 'post tag-dev'
author: ibarrond
---



In order to install the Python Packages required for a generic Data Science build, one could use the generic Anaconda, or if you're like me and you hate downloading a lot of useless stuff and controlling your environment and installed packages, you can simplily use this list by putting it into a requirements.txt file and running pip install -r requirements.txt.

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
scikit-learn

# Time Series (Only in Linux)
# pystan 
# fbprophet

