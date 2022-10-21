---
layout: post
title:  "Multirate Training of Neural Networks"
date:   2021-06-07 01:42:09 +0100
categories: jekyll update
---

In this work we propose multirate training of neural networks. <br>
We illustrate that there exist latent multiple time scales in deep learning applications (e.g., WideResNet-16 on patch-augmented CIFAR-10 data) and propose a multirate method that can learn different features present in the data by training the network on different timescales simultaneously.

Further, we use a multirate method (that partitions the network into "fast" and "slow" parts and uses linear drift) to fine-tune deep neural networks for transfer learning applications in almost half the time, without reducing the generalization performance of the resulting model. 

<img src="/pics/transfermultirate2.png" width="800"/>

This paper is joint work with Ben Leimkuhler and has been accepted to ICML 2022. <br>
The latest version can be found on the arXiv: [[paper]](https://arxiv.org/abs/2106.10771)[[errata]]({{TiffanyVlaar.github.io}}/docs/Corrigendum.pdf)[[slides]]({{TiffanyVlaar.github.io}}/slides/ICML_Multirate.pdf)[[poster]]({{TiffanyVlaar.github.io}}/docs/ICML_MultiratePoster.pdf)
<!--This work was also presented at the "ODE and SDE methods in machine learning" symposium, NUMDIFF-16, 2021.-->

