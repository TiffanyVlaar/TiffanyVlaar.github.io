---
layout: post
title:  "Gerrymandering - Evaluate fairness of Redistricting using MCMC"
date:   2019-09-18 
categories: jekyll update
---

<!--- Redrawn Constituency Boundaries using Sampling Methods -->
Gerrymandering is a term originating from US politics and involves the redrawing of constituency boundaries for the gain of a specific political party. Rule one of gerrymandering is to maximise the amount of "wasted votes" of your opposing political party, while minimising the amount for your own party. We consider votes for your party to be wasted in constituencies (also called electoral districts) where your party lost, because these votes could instead have been used to allow your party to win in neighbouring swing constituencies. Similarly, in a constituency where your party won, a significant surplus in votes for your party are also wasted, i.e., it doesn't matter if you won with 80% of the votes or 55% of the votes. There surplus votes could also be moved to change the outcome in other constituencies to your party's benefit.

![gerry1]({{TiffanyVlaar.github.io}}/pics/gerry1.png =100x20)
![gerry2]({{TiffanyVlaar.github.io}}/pics/gerry2.png =50x20)

A characteristic of gerrymandering were often thought to be weirdly-shaped boundaries (hence the name gerrymandering - originating from salamanders and the name of the guy (Governor Gerry) who first introduced the term [1]). Therefore, compactness of the drawn constituencies has often been used as a measure of fairness. However, this is neither a necessary nor sufficient condition for detecting gerrymandering [2]. Sampling methods offer a viable alternative.


 [1] Griffith, E. (1907). The Rise and Development of the Gerrymander, Chicago: Scott, Foresman and Co.

[2] Young, H. (1988). Measuring the Compactness of Legislative Districts. Legislative Studies Quarterly, 13(1), pp.105-115.