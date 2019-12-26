---
title: Logistic Regression using Python (scikit-learn)
layout: post
author: Mahmud
image: assets/images/2239751569.jpg
tutorial: false
blog: true
---

One of the most amazing things about Python’s scikit-learn library is that is has a 4-step modeling pattern that makes it easy to code a machine learning classifier. While this tutorial uses a classifier called Logistic Regression, the coding process in this tutorial applies to other classifiers in sklearn (Decision Tree, K-Nearest Neighbors etc). In this tutorial, we use Logistic Regression to predict digit labels based on images. The image above shows a bunch of training digits (observations) from the MNIST dataset whose category membership is known (labels 0–9). After training a model with logistic regression, it can be used to predict an image label (labels 0–9) given an image.