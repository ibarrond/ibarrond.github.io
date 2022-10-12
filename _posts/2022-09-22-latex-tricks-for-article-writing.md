---
layout: post
current: post
cover:  assets/images/post-setup-env.jpg
navigation: True
title: Latex tricks for article writing
date: 2022-09-22 10:00:00
tags: [dev]
class: post-template
subclass: 'post tag-dev'
author: ibarrond
---


## Cleaning up references in Bibtex
First run automatic Bibtex sorting & alignment from the [_Latex Workshop_](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension, then run this Replace command with regex enabled: `^[^@ \}]+ (.+\n)*?\}\n` (replace with nothing). This will remove all the duplicated references.