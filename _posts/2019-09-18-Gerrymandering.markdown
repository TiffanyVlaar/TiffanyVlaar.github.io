---
layout: post
title:  "Gerrymandering - Study Fairness of Political Redistricting using MCMC"
date:   2019-09-18 
categories: jekyll update
---

<!--- Redrawn Constituency Boundaries using Sampling Methods -->
Gerrymandering is a term originating from US politics and involves the redrawing of constituency/electoral districts boundaries to the benefit of a specific political party. Rule one of gerrymandering is to maximise the amount of "wasted votes" of your opposing political party, while minimising the amount for your own party. We consider votes for your party to be wasted in constituencies where your party lost, because these votes could instead have been used to allow your party to win in neighbouring swing constituencies. Similarly, in a constituency where your party won, a significant surplus in votes for your party are also wasted, i.e., it doesn't matter if you won with 80% of the votes or 55% of the votes. There surplus votes could also be moved to change the outcome in other constituencies to your party's benefit. 

![gerry1]({{TiffanyVlaar.github.io}}/pics/gerry1.png)
![gerry2]({{TiffanyVlaar.github.io}}/pics/gerry2.png)

In the pictures above I've given an example of the effect of gerrymandering for a two-party system with three constituencies. In the United Kingdom each constituency consists of a collection of wards (the individually coloured squares). These wards are used for local government, whereas each constituency as a whole will select a single MP (member of parliament) to represent the region on a national level. In the first figure, blue has a lot of surplus votes in the middle constituency, which can be moved to neighbouring constituencies to win the election there. In the second figure the boundaries have been manipulated for the advantage of the blue party, which has now won two constituencies instead of just one. The amount of wasted votes of the red party has been maximised. In practice, the gerrymandering thugs will do this by identifying areas where they are unlikely or likely to win based on historical voting data and by identifying the voting patterns of different population groups. For example, in the USA african americans typically tend to vote for the democrats. By spreading out the votes of african americans over different constituencies, republicans can manage to dissolve the influence of these votes and increase the amount of wasted votes of the democratic party.

![gerry1]({{TiffanyVlaar.github.io}}/pics/Gerrymander.png)
A characteristic of gerrymandering were often thought to be weirdly-shaped boundaries (hence the name gerrymandering - originating from a shape resembling a salamander and the name of the person (Governor Elbridge Gerry) who first introduced the term [1]). Therefore, compactness of the drawn constituencies has often been used as a measure of fairness. However, this is neither a necessary nor sufficient condition for detecting gerrymandering [2]. Sampling methods offer a viable alternative. To do so, we determine 





 [1] Griffith, E. (1907). The Rise and Development of the Gerrymander, Chicago: Scott, Foresman and Co.

[2] Young, H. (1988). Measuring the Compactness of Legislative Districts. Legislative Studies Quarterly, 13(1), pp.105-115.