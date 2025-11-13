---
layout: post
title:  "BatchNorm Layers have an Outsized Effect on Adversarial Robustness"
date:   2025-11-13 11:15:10 +0100
categories: jekyll update
---

Neural networks are well-known to be vulnerable to adversarial attacks: subtle, crafted input perturbations that cause models to misclassify. 
Adversarial training uses adversarial examples during training to strengthen models against such attacks.
Projected gradient decent has been found effective at generating adversarial examples for training. 
However, a major drawback to adversarial training is the decreased test accuracy on clean data, with an inherent trade-off between robustness and clean test accuracy.
It is well-known that different neural network layers play different roles, and this has also been considered within the context of adversarial training. In particular, Bakiskan et al. 2022 hypothesize that earlier layers are more crucial in obtaining robustness against adversarial attacks. 
Nguyen et al. 2024 show that different layers affect robust overfitting differently and argue that changing the optimization of later layers can mitigate overfitting. Relatedly, Cianfarani et al. [2] found that
"deeper layers overfit during robust training". This prior research suggests that training different neural network layers differently may benefit adversarial training. 
Batch normalization (BatchNorm) is a common part of various deep learning architectures. BatchNorm was argued to be a cause of adversarial vulnerability (Galloway et al., 2019) and removing BatchNorm layers was shown to have potential to enhance adversarial training (Wang et al., 2022). 
Although BatchNorm layers comprise only a very small amount of the trainable parameters of a model (typically less than 0.2%), it was shown that by only training BatchNorm layers non-trivial test accuracy can be obtained (Franklet et al., 2021). Inspired by this, we perform a thorough investigation into how BatchNorm layers interact with adversarial training.

This was joint work with my summer student Noam. 
If you are interested in learning more about this work, come along to the poster session at the NeurIPS 2025 Optimization for Machine Learning workshop or drop me an email. 
