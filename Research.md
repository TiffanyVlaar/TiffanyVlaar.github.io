---
layout: page
title: Research
permalink: /research/
---

**Supervision**: I have various fully funded PhD projects available. Please see [here]({{TiffanyVlaar.github.io}}/supervision) for more information. 

<!---
*Opportunities*: 
- The University of Glasgow offers 4-year fully funded PhD positions for black UK domiciled students through the James McCune Smith scholarships. Please feel free to reach out if you want to discuss applying for these. More information: [https://www.gla.ac.uk/scholarships/mccune-smith/](https://www.gla.ac.uk/scholarships/mccune-smith/)
The application deadline for Science and Engineering areas has been extended to 15 March 2024.
- Apply for a 4-year fully-funded PhD position within the [Leverhulme Programme for Doctoral Training in Ecological Data Science](https://ecological-data-science.github.io/projects.html). Together with Dr. De Clippele (main, University of Glasgow) and Dr. Smith (University of Copenhagen) we are offering a project on deploying deep learning to analyse marine acoustic & image data. *Deadline*: 22 March 2024.--->

**Research Interests**: Mathematics for Deep Learning, Physics-informed Machine Learning, Sustainable AI, AI for Biodiversity Monitoring.
<!--Sampling Methods, Numerical methods for Stochastic Differential Equations,--> 

**Papers:** <br>
Camera-Trap Image Classification Under Ground Truth Uncertainty. Accepted to NeurIPS Tackling Climate Change with Machine Learning 2025 Workshop. Full paper under review.

BatchNorm Layers have an Outsized Effect on Adversarial Robustness. Accepted to NeurIPS Optimization for Machine Learning 2025 Workshop. [[blog]]({{TiffanyVlaar.github.io}}/jekyll/update/2025/11/13/batchnorm)

Using machine learning effectively in marine benthic ecology: a question-driven toolkit. Led by L. De Clippele. Under Review.

DeepSea Nexus: Exploring perspectival connection with oceans data in virtual reality. Planned 2025.

[Normalization Layers Are All That Sharpness-Aware Minimization Needs [blog]]({{TiffanyVlaar.github.io}}/jekyll/update/2023/09/26/SAMON)[[paper]](https://arxiv.org/abs/2306.04226)[[poster]]({{TiffanyVlaar.github.io}}/docs/SAM_ON_poster_NeurIPS2023.pdf), *NeurIPS* 2023. <br>
Applying sharpness-aware minimization (SAM) only to the normalization layers of a network can enhance generalization performance, while reducing computational cost.

[Multirate Training of Neural Networks [blog]]({{TiffanyVlaar.github.io}}/jekyll/update/2021/10/07/Multirate)[[paper]](https://arxiv.org/abs/2106.10771)[[errata]]({{TiffanyVlaar.github.io}}/docs/Corrigendum.pdf)[[slides]]({{TiffanyVlaar.github.io}}/slides/ICML_Multirate.pdf)[[poster]]({{TiffanyVlaar.github.io}}/docs/ICML_MultiratePoster.pdf), *ICML 2022*. <br>
The developed multirate approach can be used to fine-tune deep neural networks for transfer learning applications in almost half the time, without reducing generalization performance.

[What can linear interpolation of neural network loss landscapes tell us? [blog]]({{TiffanyVlaar.github.io}}/jekyll/update/2021/10/02/LinearInterpolation)[[paper]](https://proceedings.mlr.press/v162/vlaar22a.html)[[slides]]({{TiffanyVlaar.github.io}}/slides/ICML_LinearInterpolation.pdf)[[poster]]({{TiffanyVlaar.github.io}}/docs/Poster_LinearInterpolation_ICML.pdf), *ICML 2022*. <br>
Neural network loss landscapes are difficult to visualize due to their high-dimensionality and the complicated nature of the actual optimization path. This motivated the use of the loss along the linear path between the initial and final parameters of a neural network as a crude yet simple measure of the loss landscape. Prior work used this to draw broader conclusions about the difficulty of the optimization problem. In this paper, we put inferences of this kind to the test and study the role played by individual layers and substructures of the network.

[Better Training using Weight-Constrained Stochastic Dynamics [blog]]({{TiffanyVlaar.github.io}}/jekyll/update/2020/11/04/ConstraintBasedReg), *ICML 2021*. <br>
In this paper we use constrained stochastic differential equations to train deep neural networks. We provide a general framework with accompanying discretization schemes and a statistical guarantee on the convergence of the
training. This general framework enables the implementation of powerful new constraints, such as orthogonality of the weight matrix. <br>
Related workshop paper [Constraint-based Regularization of Neural Networks](https://arxiv.org/abs/2006.10114) *was accepted as spotlight presentation for NeurIPS 2020 Optimization for ML workshop and received the best student paper award.* Presentation: [YouTube link](https://youtu.be/5xhvuNPmCj4) <br>

[Partitioned Integrators for Thermodynamic Parameterization of Neural Networks]({{TiffanyVlaar.github.io}}/jekyll/update/2019/08/31/NewPaper.html)*, Foundations of Data Science 1 (4) , 457-489 (2019). Accepted as digital acceptance to NeurIPS 2019 Machine Learning and the Physical Sciences workshop.* <br>
This thermodynamic parameterization technique for neural network training allows for enhanced exploration of problems with complicated loss landscapes, which are thought to arise in molecular dynamics applications.

<!---Check out my new blogpost about the paper [here]({{TiffanyVlaar.github.io}}/jekyll/update/2019/08/31/NewPaper.html)-->

**Other Research Projects:**
- [DeepSea Nexus: Connecting with your oceans through Extended Reality]({{TiffanyVlaar.github.io}}/jekyll/update/2025/06/04/deepseanexus.html). Crucible grant, in collaboration with L. De Clippele and I. Findlay-Walsh.
- Coding, creativity and confidence in the Generative Artificial Intelligence era. Crucible grant, in collaboration with C. Reid, G. Callea, R. Yanagida, and S. Falkowski. [Coding workshop files]({{TiffanyVlaar.github.io}}/jekyll/update/2025/06/04/codingAIera.html)
- Interactive machine learning reflections on how a human-in-the-loop approach can increase model training efficiency, led by L. De Clippele and presented at Marine Imaging Workshop 2024.
- Deep learning framework for the unit commitment problem in electric power systems.
- Gerrymandering in the United Kingdom: Interpreting political geography in a statistical physics framework and using Markov Chain Monte Carlo methods for Assessing the Fairness of Political Constituencies. Related blogpost: [Gerrymandering blog]({{TiffanyVlaar.github.io}}/jekyll/update/2019/11/18/Gerrymandering.html)
- Introducing sparsity in neural networks using sampling. <br>
  Some related posts: [Generalization Error]({{TiffanyVlaar.github.io}}/jekyll/update/2019/03/27/Generalization.html), [Sparsity in Neural Networks]({{TiffanyVlaar.github.io}}/jekyll/update/2019/05/10/Sparsity.html), [Loss Landscape]({{TiffanyVlaar.github.io}}/jekyll/update/2019/07/20/LossLandscape.html).
 - Limitations of using test accuracy as the sole metric for model evaluation by examining neural network behavior at the classification boundary. Accepted to NeurIPS 2021 I (Still) Can’t Believe It’s Not Better (ICBINB) workshop. <br>
- Applying Bayesian inference techniques to stochastic models (in particular Langevin dynamics models) for flocking.
- Stochastic multiple timestepping techniques for coupled systems of fast and slow variables.
- From my days at the Perimeter Institute for Theoretical Physics, a study on the shape dependence of two-cylinder Rényi entropies for free bosons on a lattice, which [appeared in Physical Review B](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.94.165136).

**Supervision**: 
- Viktor Wu. The marine rewilding effect: Building a cost-effective framework for measuring Marine Net Gain project with Dr. De Clippele (main, University of Glasgow), Dr. Hogdson (CreditNature), and Dr. Wartmann (University of Aberdeen) within the [NETGAIN CDT](https://netgain.wp.st-andrews.ac.uk).
- Antonella Marsella through the DiveIn CDT. Jointly supervised with Prof. Fani Deligianni (main, Computing Science) and Dr. Stuart Grey (James Watt School of Engineering)
- Tobias Froehlich through the DiveIn CDT. Jointly supervised with Dr. Lauritz Thamsen (main) and Prof. Wim Vanderbauwhede in Computer Science.
- Fay Bennedik. Statistical methods for abundance estimation using emerging data types with Prof. McCrea (Lancaster University, main), Prof. Torney (main, University of Glasgow), Prof. Morales (University of Glasgow), Dr. Wallin (Lancaster University) within the [ExaGEO CDT](https://www.exageo.org).
- Deploying deep learning for marine biodiversity monitoring with Dr. De Clippele (main, University of Glasgow) and Dr. Smith (University of Copenhagen) within the Leverhulme Programme for Doctoral Training in Ecological Data Science.
- Two AIMS Ghana MSc in Mathematical Sciences students.
- Level 4 Projects on neural network optimisation.
- MSci project with industry co-supervisor Dr. Hodgson (CreditNature) on Simulating Scottish Ecosystems for Landscape Ecology Metrics.
- Machine learning for camera trap image classification, EPSRC Vacation Project with Dr. Peter Stewart (University of Glasgow).
- UG Summer Research project on Monitoring vegetation patterns from drone imagery using machine learning, with Dr. Eizenhöfer (University of Glasgow).
- Summer Research Project on Layer-wise training of neural networks and adversarial robustness.
- Effective nonlinearity and effective capacity of deep neural networks, Master Thesis Project, with Dr. Pinson (main, Eindhoven University of Technology).

**Selected Research Engagement**: <!--, Workshops, and Summerschools:**-->
- Plenary Talk, Martingale Scholar Away Day, 2026.
- Invited Talk, 30th Biennial Numerical Analysis Conference, Numerical Analysis and AI Minisymposium, 2025.
- Invited Talk, Technology-Enhanced Mathematical Sciences Education seminar, 2026.
- Keynote Talk with C. Reid, Future Education conference, 2025.
- Talk, A Network for Teaching and Learning in Scottish HE Mathematical Sciences, 2025.
- Organizer, Computing Science Meets Maths & Stats Lightning Talk, University of Glasgow, 2025.
- Organizer, [Network on Mathematical Data Science for Materials Science](https://sites.google.com/site/xiaochengshang/network), 2025.
- Seminar Talk, Data Science and Computational Statistics Seminar at the University of Birmingham, 2024.
- Talk with C. Reid, Lovelace-Hodgkin Symposium on AI Ethics, 2024.
- Invited Talk, Underwater Image Analysis from A to Z workshop, 2024.
- Invited Talk, Oberwolfach meeting on Constrained Dynamics, Stochastic Numerical Methods and the Modeling of Complex Systems, 2024.
- Invited Talk, New Directions for Stochastic Differential Equations and Machine Learning, ICMS workshop, 2024.
- Paper at NeurIPS, 2023.
- Invited Talk, Montreal Machine Learning and Optimization Seminar, 2023.
- Invited Talk, CRM Applied Mathematics Lab Seminar, 2023.
- Invited Talk, RMT-OPT-ML Seminar, 2023.
- Invited Talk, Mathematics of Machine Learning session, CMS Summer Meeting, 2023.
- Organizer, Mathematical and Empirical Understanding of Foundation Models Workshop, ICLR 2023.
- Talk, Oxford Data Science seminar, Mathematical Institute, 2023.
- Two spotlight talks and posters at ICML, 2022.
- Poster, "Interacting particle dynamics and data science" ICMS workshop, 2022.
- Talk at "ODE and SDE methods in machine learning" symposium, NUMDIFF-16, 2021.
- Poster at Theory of Deep Learning workshop, Newton Institute, Cambridge, 2021.
- Talk and poster presenter at ICML 2021.
- Spotlight presentation at NeurIPS 2020 Optimization for ML workshop, December 2020.
- Statistical Physics & Machine Learning summer school, Les Houches, July 2020.
- Machine Learning Summer School (MLSS), Tuebingen, June 2020.
- Invited talk at Structural Inference in High Dimensional models, Mathematics of Learning conference, Bordeaux, 2020. Cancelled due to pandemic.
<!-- Poster at Foundations of Computational Mathematics, 2020. Cancelled due to pandemic.-->
- Research Collaboration Visit Gabriel Stoltz (CERMICS, Ecole des Ponts ParisTech), 2020. Cancelled due to pandemic.
- Molecular Simulation and Machine Learning conference, Temple University, Rome, January 2020.
- Sampling algorithms on manifolds workshop, Isaac Newton Institute, Cambridge, November 2019.
- Invited Poster presentation at Amazon Research Days, Edinburgh, November 2019.
- Research Collaboration Visit at Courant Institute, NYU, October 2019. Discussions with Joan Bruna, Stanislaw Jastrzebski, Mark Tuckerman, Eric Vanden-Eijnden, and Jonathan Weare (host).
- Talk at Alan Turing’s UK-Japan robotics & AI research collaboration workshop, 2019.
- Gene Golub SIAM summerschool on High-Performance Data Analytics, June 2019.
- CECAM - Computational mathematics for model reduction and predictive modelling in molecular and complex systems, May 2019.
- ICMS - Modelling Camp, May 2019.
<!--- MIGSAA Advanced PhD Course - Diffusion Processes, Autumn 2018.-->
- Poster presentation at CSide Conference, University of Glasgow, November 2018.
<!--- i-like Workshop, Newcastle University, June 2018.-->
<!--- Masterclass Prof. David Dunson (Duke University) on Scalable Bayesian Inference, 2018.-->
<!---Alan Turing Institute - Data-driven modelling of complex systems, May 2018.-->





