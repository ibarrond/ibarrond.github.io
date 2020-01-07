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

Overfitting is one of the most common issues you might find when training a Deep Learning algorithm. Here are some strategies on how to overcome it (many more available out there!).

In short, you need to increase the generalization of your network. Here are some ways to do so:

1. Get more training data (expensive? not always possible/useful?)
2. Reduce the capacity (degrees of liberty or complexity) of the network (smaller achitecture for a not so big problem/dataset). Alternatively one can use architectures that generalize quite well, such as the inverted convolutional pyramid comonly found in image classification.
3. Add weight regularization.
4. Add dropout.
5. Data augmentation.
6. Batch Normalization. From the original paper: `Batch normalization reduces the dependence of your network to your weight initialization. Adds regularization into your network.`
7. Modify learning rate and/or batch size.
8. Read this article, understand it an put it in practice (this is good stuff, really): https://arxiv.org/pdf/1803.09820.pdf
