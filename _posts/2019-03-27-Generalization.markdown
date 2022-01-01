---
layout: post
title:  "Generalization Error"
date:   2019-03-27 
categories: jekyll update
---

In this post I want to talk about generalization. The question of whether or not your trained neural network generalizes to unseen (test) data forms the core of machine learning research. We are aware of many factors that influence the generalization capacity of a trained neural network, such as the size of the network, the activation functions, the initialization, the optimizer, and the stopping criterion - but we are lacking a theory that connects all of them. The statistical learning theory research field [1] offers several complexity measures [2,3], but these are all incapable of explaining all features of the generalization behaviour of overparameterized neural networks [4]. They are still interesting to study though, so I will first describe these and then move on to some more recent approaches.

There are two sources of error in neural networks [1]:
<ol>
<li> Approximation Error: caused by the choice of architecture of the neural network - each architecture has a limited expressive power. </li>
<li> Estimation Error: caused by the difference between the ideal parameters and the learned parameters, given a specific neural network architecture. </li>
</ol>
Estimation error can be reduced by having a larger training set (thus leading to a better parameterization of the neural network). The approximation error can be reduced by using larger networks, but if this leads to overfitting, the estimation error is increased. 

There are two classic complexity measures for the chosen neural network architecture: the VC-dimension [2] and the Rademacher complexity [3].
<ol>
<li> VC-dimension: defined as the largest dataset size on which one can obtain zero training error using this network architecture. It effectively measures the network's capacity. </li>
<li> Rademacher complexity: measures the network's ability to fit random labels. </li>
</ol>

Unfortunately, these measures were shown to be ineffective for measuring generalizability of overparameterized neural networks [4]: deep neural networks have the capacity to memorize the training data (which means the VC-dimension can't be used as a generalization bound) and architectures with good performance on real labels can simultaneously easily fit random labels (hence Rademacher complexity can't be used). Additionally, regularization techniques, which are used to combat overfitting by reducing the Rademacher complexity, are ruled ineffective for neural networks as they do not reliably change the generalization error.

We therefore need to turn to more recent ideas to find complexity measures that can capture more properties of neural networks, especially ones that can explain why overparameterized neural networks don't overfit [5]. One well-known complexity measure is the sharpness of obtained minima [6,7]. Here sharpness of a minimum is measured by studying the eigenvalues of the Hessian.  Flatter minima are thought to be more robust to perturbations in the parameters and have lower description lengths (because moving away from a flat minima doesn't lead to a large error, so using less precision in the description of a flat minima is fine), which is better according to the minimum description length principle [8,9]. However, sharpness is not a scale invariant measure [10,11] - so some care must be taken in using this as a complexity measure. Some efforts were made to combine this idea with a norm-based complexity measure [11], where the norm-based approach is based on the idea that we should look at the size of the weights rather than at the amount of weights for our complexity measure [12,13]. However, neither of these approaches explain the generalization capacity of overparameterized neural networks.

A different line of research relates compressibility of neural networks to their generalization ability. Zhou et al. [14] for example argue that it is more difficult to compress neural networks that overfit. Arora et al. [15] argue that networks with a higher noise stability can be compressed more - because noise stability means that the "noise" introduced by compressing the neural network is attenuated by later layers of the network. Noise stability is closely related to the concept of flat minima discussed before. Neural networks that can be compressed without a significant loss in accuracy, can be shown to (in their compressed form) generalize well.

There are many other papers that propose complexity measures, but we haven't found our holy grail yet - our search for finding a complexity measure that can explain all generalizability features of neural networks continues. 

***References*** <br>
[1] S. Shalev-Shwartz and S. Ben-David. Understanding Machine Learning: From Theory to Algorithms. Cambridge University Press, 2014.

[2] V. N. Vapnik and A. Chervonenkis. The necessary and sufficient conditions for consistency of the method of empirical risk minimization. Pattern Recognition and Image Analysis, 1(3):284–305, 1991.

[3] P.L. Bartlett and S. Mendelson. Rademacher and Gaussian complexities: Risk bounds and structural results. Journal of Machine Learning Research, 3:463–482, 2002.

[4] C. Zhang, S. Bengio, M. Hardt, B. Recht, and O. Vinyals. Understanding deep learning requires rethinking generalization. International Conference on Learning Representations, 2017.

[5]  B. Neyshabur, R. Tomioka, and N. Srebro. In search of the real inductive bias: On the role of implicit regularization in deep learning. Proceeding of the International Conference on Learning Representations workshop track, 2015.

[6] N.S. Keskar, D. Mudigere, J. Nocedal, M. Smelyanskiy, and P.T.P. Tang. On large
batch training for deep learning: Generalization gap and sharp minima. ICLR, 2017.

[7] P. Chaudhari, A. Choromanska, S. Soatto, Y. LeCun, C. Baldassi, C. Borgs, J. Chayes, L. Sagun, and R. Zecchina. Entropy-SGD: Biasing gradient descent into wide valleys. ICLR, 2017.

[8] G. E. Hinton and D. van Camp. Keeping the neural networks simple by minimizing the description length of the weights. Proceedings of the Sixth Annual Conference on Computational Learning Theory, pages 5–13, 1993.

[9] S. Hochreiter and J. Schmidhuber. Flat minima. Neural Computation, 9(1):1–42, 1997.

[10] L. Dinh, R. Pascanu, S. Bengio, and Y. Bengio. Sharp minima can generalize for deep nets. ICML, 2017.

[11] B. Neyshabur, S. Bhojanapalli, D. McAllester, and N. Srebro. Exploring generalization in deep learning. Advances in Neural Information Processing Systems, pages 5949–5958, 2017.

[12] P. L. Bartlett. The sample complexity of pattern classification with neural networks: the size of the weights is more important than the size of the network. IEEE transactions on Information Theory, 44(2):525–536, 1998.

[13] B. Neyshabur, R. Tomioka, and N. Srebro. Norm-based capacity control in neural networks. Proceeding of the 28th Conference on Learning Theory, 2015.

[14] W. Zhou, V. Veitch, M. Austern, R. P. Adams, and P. Orbanz. Vacuous generalization bounds at the ImageNet scale: a PAC-Bayesian compression approach. ICLR, 2019.

[15] S. Arora, R. Ge, B. Neyshabur, and Y. Zhang. Stronger generalization bounds for
deep nets via a compression approach. ICML, 2018.

