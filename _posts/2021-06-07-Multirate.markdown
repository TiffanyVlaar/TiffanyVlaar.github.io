---
layout: post
title:  "Multirate Training of Neural Networks"
date:   2021-06-07 01:42:09 +0100
categories: jekyll update
---

In this work we propose multirate training of neural networks. <br>
We illustrate that there exist latent multiple time scales in deep learning applications (e.g., WideResNet-16 on patch-augmented CIFAR-10 data) and propose a multirate method that can learn different features present in the data by training the network on different timescales simultaneously.

Further, we use a multirate method (that partitions the network into "fast" and "slow" parts and uses linear drift) to fine-tune deep neural networks for transfer learning applications in almost half the time, without reducing the generalization performance of the resulting model. 
<!---: partitioning neural network parameters into "fast" and "slow" parts which are trained simultaneously using different learning rates.-->
<!---***Latent multiple time scales in deep learning *** <br>-->

<img src="/pics/transfermultirate.png" width="800"/>

This paper is joint work with Ben Leimkuhler. <br>
[arXiv preprint:2106.10771](https://arxiv.org/abs/2106.10771)


[Slides]({{TiffanyVlaar.github.io}}/slides/Multirate_Numdiff.pdf) for my talk at the "ODE and SDE methods in machine learning" symposium, NUMDIFF-16, 2021.

