---
layout: post
current: post
cover:  assets/images/post_overfitting.png
navigation: True
title: Overfitting must be avoided
date: 2018-09-29 08:00:00
tags: [Deep Learning]
class: post-template
subclass: 'post tag-deep-learning'
author: ibarrond
---

Overfitting is one of the most common issues you might find when training a Deep Learning algorithm. Here are some strategies on how to overcome it (non exhaustive list).

In short, you need to increase the generalization of your network. Here are some ways to do so:

1. Get more training data (expensive? not always possible/useful?)
2. Reduce the capacity (degrees of liberty or complexity) of the network (smaller achitecture for a not so big problem/dataset). Alternatively one can use architectures that generalize quite well, such as the inverted convolutional pyramid comonly found in image classification.
3. Add weight regularization (or other kinds of regularization)
4. Add dropout. It acts as a natural regularizer.
5. Data augmentation, to artificially increase the amount of data you have while still keeping it meaningful.
6. Batch Normalization. From the original paper: `Batch normalization reduces the dependence of your network to your weight initialization. Adds regularization into your network.`
7. Hyperparameter tuning: Modify learning rate, batch size... to find the sweet configuration that works. As an aditional source, I suggest reading ["A Disciplined Approach to Neural Network Hyper-Parameters"](https://arxiv.org/pdf/1803.09820.pdf) by Leslie N. Smith.