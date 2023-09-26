---
layout: post
title:  "What can linear interpolation of neural network loss landscapes tell us?"
date:   2021-10-02 05:42:09 +0100
categories: jekyll update
---

Neural network loss landscapes are notoriously difficult to visualize. A common way to address this is to plot linear slices of the landscape, for example from the initial state of the network to the final state after optimization [1]. Although this inherently sacrifices information, the linear interpolation technique is seen as "a simple and lightweight method to probe neural network loss landscapes" [2] and is therefore frequently used [2-6].

An absence of obstacles along the linear path is frequently cited as an indication that "tasks are relatively easy to optimize" [1], where "the walk could just as well have taken a straight line without encountering any obstacles" [7]. 

In this paper we put to the test whether using the popular 1D linear interpolation technique actually relates to success of optimization. Further, we introduce several novel modes of analysis, including the use of linear interpolation to study the role played by individual layers and substructures of the network. We find that:
<ol>
<li> The shape of the linear path is in fact not a reliable indicator of test accuracy. </li>
<li> Custom per-layer optimization schemes can be obtained by studying the shape of the linear path of different layers. </li>
 <li> Layers have different levels of sensitivity to the choice of initialization. We introduce the concept of partial pre-training, where we initialize some layers to a trained (on CIFAR-10) or pre-trained (on ImageNet) state, while using random initialization for others. Doing so surprisingly leads to worsened test accuracy and (uncorrelated) effects on the shape of the linear path. </li>
</ol>

This paper is joint work with Jonathan Frankle (MIT, MosaicML) and has been accepted to ICML 2022.
[arXiv:2106.16004](https://arxiv.org/abs/2106.16004)


*References* <br>
[1] I.J. Goodfellow, O. Vinyals, and A.M. Saxe. Qualitatively characterizing neural network
optimization problems. ICLR, 2015. <br>
[2] J. Lucas, J. Bae, M. Zhang, J. Ba, R. Zemel, and R. Grosse. On monotonic linear interpolation of neural network parameters. OptML NeurIPS workshop, 2020. <br>
[3] S. Fort and S. Jastrzebski. Large scale structure of neural network loss landscapes. ICML, 2019. <br>
[4] Y. Hao, L. Dong, F. Wei, and K. Xu. Visualizing and understanding the effectiveness of BERT. 
EMNLP, 2019. <br>
[5] S. Jastrzebski, Z. Kenton, D. Arpit, N. Ballas, A. Fischer, Y. Bengio, and A. Storkey. Three factors influencing minima in SGD. ICANN, 2018. <br>
[6] B. Neyshabur, H. Sedghi, and C. Zhang. What is being transferred in transfer learning? NeurIPS, 2020. <br>
[7] C. Li, H. Farkhoor, R. Liu, and J. Yosinski. Measuring the intrinsic dimension of objective
landscapes. ICLR, 2018. <br>


