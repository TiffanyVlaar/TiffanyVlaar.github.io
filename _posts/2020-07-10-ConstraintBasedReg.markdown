---
layout: post
title:  "Constraint-Based Regularization of Neural Networks"
date:   2020-07-10 01:42:09 +0100
categories: jekyll update
---

In this paper we use constrained stochastic differential equations (SDEs) to train deep neural networks (NNs).Constraints provide direct control of the parameter space of a model and hence afford a means to improve its generalization performance. We provide a well-founded mathematical framework to study regularized training methods for deep NNs as discretizations of constrained Langevin dynamics. Our approach has two fundamental advantages: (i) it covers most existing learning methods as well as many potential new approaches (including new constraints) and (ii) it is founded on a rigorous theoretical analysis. 

***Why is this important?*** <br>
Imposing good priors on NNs improves performance. E.g. convolutional networks suit image datasets better than heavily parameterized fully connected networks, despite being a subset of the latter (d’Ascoli et al., NeurIPS 2019). Our framework enables the implementation of powerful new constraints, e.g., sparsity-inducing or symmetries.

***What are our contributions?*** <br> 
As far as we are aware, we are the first to consider constrained SDEs to analyze the training process in machine learning. In this framework, we provide a statistical guarantee on the convergence of the training. Second, we provide detailed implementation schemes and testing to show that
the approach stands up to scrutiny. Code to complement our training methods will be released soon!

You can find a preprint on [arXiv 2006.10114](https://arxiv.org/abs/2006.10114)

