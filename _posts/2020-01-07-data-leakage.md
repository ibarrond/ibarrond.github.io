---
layout: post
current: post
cover:  assets/images/post-data-leakage.jpg
navigation: True
title: Data Leakage in Machine Learning
date: 2020-01-07 10:00:00
tags: [Data Science]
class: post-template
subclass: 'post tag-data-science'
author: ibarrond
---

Data Leakage refers to the inclusion of unfair information in the training data of a machine learning model, allowing the algorithm to "cheat" when making predictions.

This phenomenon renders a model excessively optimistic or even useless in the real world, since the model tends to leverage greatly on the unfairly acquired information. Some typical cases are:

- Leaking test data into the training data. 
- Leaking the correct prediction into the test data.
- Leaking of information from the future into the past.
- Reversing of intentional obfuscation, randomization or anonymization.
- Inclusion of data not present in the model’s operational environment.
- Distorting information from samples outside of scope of the model’s intended use.

# Accidental Leakage
Data leakage is mostly accidental in real world cases. **Preprocessing a dataset before splitting into training/test** leads to non-intentional leakage: normalization, augmentation followed by shuffling, dimensionality reduction or feature selection.  **Duplicated data** that ends up in both the training and the test set are also a souce of leakage, as are **future data that slips into past data prediction** (say a batch normalization with an RNN or LSTM, or more simplily future trend information on a stock market prediction).

# Intentional Leakage
Leakage is especially challenging in machine learning competitions. In normal situations, leaked information is typically only used accidentally. But in competitions, participants often find and intentionally exploit leakage where it is present.

An early Kaggle competition, Link Prediction for Social Networks, makes a good case study in this. There was a sampling error in the script that created that dataset for the competition: a > sign instead of a >= sign meant that, when a candidate edge pair had a certain property, the edge pair was guaranteed to be true. A team exploited this leakage to take second in the competition.

Furthermore, the winning team won not by using the best machine-learned model, but by scraping the underlying true social network and then defeated anonymization of the nodes with a very clever methodology. In fact, “the concept of identifying and harnessing leakage has been openly addressed as one of three key aspects for winning data mining competitions” ([source](http://www.cs.umb.edu/~ding/history/470_670_fall_2011/papers/cs670_Tran_PreferredPaper_LeakingInDataMining.pdf))

# Recipes to avoid Data leakage
1. *Remove correlations in dataset*: make sure there are no correlated variables between input and prediction.
2. *Drop duplicates*.
3. *Ensure temporal coherence*: you should never use information coming from the future to make predictions.
4. *Split dataset in train/validation/test before any preprocessing*: avoid contamination. Do not touch validation/test sets!
5. *Use your test dataset only ONCE*. Do not use it to tune hyperparameters! That is what the Validation set is for.
6. *Investigate results*: Is the performance too good for a simple algorithm? Is there a single feature driving the prediction? 

---------

> Sources: [kaggle](https://www.kaggle.com/docs/competitions#leakage), [reddit](https://www.reddit.com/r/MachineLearning/comments/965zgf/d_tell_me_about_how_you_were_a_victim_of_data/), [DevinSoni@towardsdatascience](https://towardsdatascience.com/data-leakage-in-machine-learning-10bdd3eec742), [MaxTingle@towardsdatascience](https://towardsdatascience.com/preventing-data-leakage-in-your-machine-learning-model-9ae54b3cd1fb)