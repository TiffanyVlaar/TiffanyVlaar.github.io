---
layout: post
title:  "Loss Landscape"
date:   2019-06-17 
categories: jekyll update
---

The loss landscape of neural networks is a complex and under-developed concept. In the last two years there has been more active research in this area due to a conjecture that connected the shape of minima with their generalization capacity [1, 2, 3]. Although the veracity of this conjecture has since been disputed [4], it still succeeded in bringing the study of loss landscapes of neural networks back into the spotlight. There is now a growing interest in visualizing the loss landscape of neural networks, which resulted in some interesting papers [5, 6]. However, there are still a lot of open questions to be answered, especially regarding how the loss landscape changes due to different architecture and algorithm choices and how this affects the generalization error of the neural network. In this chapter we will summarize the most important results obtained to date.

Loss landscapes are difficult to interpret due to their high-dimensionality and non- convexity. One would expect that optimizers are likely to get stuck in isolated local minima, but this was disputed by Goodfellow et al. [7], who show that a large variety of neural networks never encounter any obstacles on their optimization path, i.e., the path from the initial to the final optimization step typically decreases monotonically. This explains the success of SGD in optimizing neural networks, despite the non-convexity of the objective functions. Additionally, our low-dimensional intuitions often do not translate to the high-dimensional case: critical points with high error are exponentially likely to be saddle points, rather than local minima, which means that saddle points are thought to be the more likely cause of a possible impediment of optimisation [8]. Studies of the Hessian of the loss function also imply that the traditional notion of isolated basins is incorrect, as they show that as optimization progresses there is an abundance of flat directions, with the large majority of the eigenvalues being (close to) zero [9, 10].

Li et al. [11] show that optimization can be constrained to a relatively low-dimensional, randomly generated subspace of the full parameter space and still obtain good test accuracy. Fort and Scherlis [12] confirmed this result and noted the importance of initialization. The lowest possible dimension at which good solutions occur is called the "intrinsic dimension" of the problem. The approach from Li et al. [11] can be used for compression purposes, but also helps us to understand the structure of the loss landscape better. The authors find that the intrinsic dimension does not change much for different neural network sizes. This seems to imply that after having enough parameters to solve the problem, the extra parameters are used to increase the dimension of the solution manifold.

Fort and Jastrzebski [6] model a D-dimensional loss surface as the union of inter- connected high-dimensional manifolds (called "wedges"), with dimensions n < D. Op- timization procedures starting with different initializations lead to minima on different wedges. They show that there exist low-loss subspaces that connect these sets of different minima (this was also argued by [13, 14] for pairs of minima). So one can move from each wedge to another wedge through a low-loss connector. Different wedges are thought to correspond to different sets of functions. Higher learning rates, smaller batch sizes and stronger regularization strengths, are all claimed to have a similar effect on the geometrical properties of the path that the optimizer (SGD) travels, namely they increase the distance between an optimum and a high loss area by affecting the curvature of the exploration region.


References
[1] N.S. Keskar, D. Mudigere, J. Nocedal, M. Smelyanskiy, and P.T.P. Tang. On large batch training for deep learning: Generalization gap and sharp minima. ICLR, 2017.

[2] P. Chaudhari, A. Choromanska, S. Soatto, Y. LeCun, C. Baldassi, C. Borgs, J. Chayes, L. Sagun, and R. Zecchina. Entropy-SGD: Biasing gradient descent into wide valleys. ICLR, 2017.

[3] S. Hochreiter and J. Schmidhuber. Flat minima. Neural Computation, 9(1):1–42, 1997

[4] L. Dinh, R. Pascanu, S. Bengio, and Y. Bengio. Sharp minima can generalize for deep nets. ICML, 2017.

[5] H. Li, Z. Xu, G. Taylor, C. Studer, and T. Goldstein. Visualizing the loss landscape of neural nets. NIPS, pages 6389–6399, 2018.

[6] S. Fort and S. Jastrzebski. Large scale structure of neural network loss landscapes. arXiv: 1906.04724, ICML, 2019.

[7]  I.J. Goodfellow, O. Vinyals, and A.M. Saxe. Qualitatively characterizing neural network optimization problems. ICLR, 2015.

[8] Y. Dauphin, R. Pascanu, C. G\"{u}lc`{e}hre, K. Cho, S. Ganguli, and Y. Bengio. Identifying and attacking the saddle point problem in high-dimensional non-convex optimization. NIPS, 2014.

[9] L. Sagun, L. Bottou, and Y. LeCun. Singularity of the hessian in deep learning. ICLR, 2017.

[10] L. Sagun, U. Evci, U. G\"{u}ney, Y. Dauphin, and L. Bottou. Empirical analysis of the hessian of over-parametrized neural networks. ICLR, 2018.

[11] C. Li, H. Farkhoor, R. Liu, and J. Yosinski. Measuring the intrinsic dimension of objective landscapes. arXiv:1804.08838, 2018.

[12] S. Fort and A. Scherlis. The goldilocks zone: Towards better understanding of neural network loss landscapes. arXiv:1807.02581, 2018.

[13] F. Draxler, K. Veschgini, M. Salmhofer, and F. A. Hamprecht. Essentially no barriers in neural network energy landscape. arXiv:1803.00885, 2018.

[14] T. Garipov, P. Izmailov, D. Podoprikhin, D. P. Vetrov, and A. G. Wilson. Loss surfaces,
mode connectivity, and fast ensembling of DNNs. NIPS, 31:8789–8798, 2018.
