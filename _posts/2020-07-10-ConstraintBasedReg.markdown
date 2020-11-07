---
layout: post
title:  "Constraint-Based Regularization of Neural Networks"
date:   2020-07-10 01:42:09 +0100
categories: jekyll update
---

In this paper we use constrained stochastic differential equations (SDEs) to train deep neural networks (NNs). Constraints provide direct control of the parameter space of a model and hence afford a means to improve its generalization performance. 

***Why is this important?*** <br>
Imposing good priors on NNs improves performance. E.g. convolutional networks suit image datasets better than heavily parameterized fully connected networks, despite being a subset of the latter (d’Ascoli et al., NeurIPS 2019). We propose a general framework that enables the implementation of powerful new constraints, e.g., sparsity-inducing or symmetries. Using constraints also arises naturally in the control
of vanishing/exploding gradients. Constraints can be used to control the magnitudes of individual
weights and/or to limit the growth of gradients in deep NNs. For this purpose we propose two specific constraints, namely circle and orthogonality constraints, in our paper.  

***What are our contributions?*** <br> 
As far as we are aware, we are the first to consider constrained SDEs for neural network training. We provide a general framework with accompanying discretization schemes that allows for user-defined constraints. In this framework, we provide a statistical guarantee on the convergence of the training. We also provide detailed implementation schemes for two specific constraints and testing to show that the approach stands up to scrutiny. Code to complement the paper will be released soon!

You can find a preprint on [arXiv 2006.10114](https://arxiv.org/abs/2006.10114)

