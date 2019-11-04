---
layout: post
title:  "Gerrymandering - Study Fairness of Political Redistricting using MCMC"
date:   2019-09-18 
categories: jekyll update
---

<!--- Redrawn Constituency Boundaries using Sampling Methods -->
***What is gerrymandering?***
Consider a state X where 30% of voters vote for the blue party and 70% of voters vote for the red party. You'd expect that X's elected representatives would therefore be 30% blue and 70% red. But this is not the case in X. Instead, 60% of X's representatives are blue, and 40% are red.

This is because in 2010, the blue party gerrymandered X. That is to say, blue redrew X's electoral district boundaries maps to its advantage in order to minimise their "wasted" votes and maximise that of their opponents. 
<!---Gerrymandering is a term originating from US politics and involves the redrawing of constituency/electoral district boundaries to the benefit of a specific political party. Rule one of gerrymandering is to maximise the amount of "wasted votes" of your opposing political party, while minimising the amount for your own party. -->
We consider votes for your party to be wasted in constituencies where your party lost, because these votes could instead have been used to tip a closer election in your party's favour in a neighbouring swing constituency. Similarly, in a constituency where your party won, a significant surplus in votes for your party are also wasted votes, i.e., it doesn't matter if you won with 80% of the votes or 55% of the votes. These surplus votes would have been better spent elsewhere. 

![gerry1]({{TiffanyVlaar.github.io}}/pics/gerry1.png)
![gerry2]({{TiffanyVlaar.github.io}}/pics/gerry2.png)

In the pictures above I've given an example of the effect of gerrymandering for a two-party system with three constituencies. In the United Kingdom each constituency consists of a collection of wards (the individually coloured squares). These wards are used for local government, whereas each constituency as a whole will select a single MP (member of parliament) to represent the region on a national level. In the first figure, blue has a lot of surplus votes in the middle constituency, which can be moved to neighbouring constituencies to win the election there. In the second figure the boundaries have been manipulated for the advantage of the blue party, which has now won two constituencies instead of just one. The amount of wasted votes of the red party has been maximised.

<!---In practice, the gerrymandering people will do this by identifying areas where they are very unlikely or very likely to win based on historical voting data and by identifying the voting patterns of different population groups. For example, in the USA african americans typically tend to vote for the democrats. By spreading out the votes of african americans over different constituencies, republicans can manage to dissolve the influence of these votes and increase the amount of wasted votes of the democratic party.-->

A characteristic of gerrymandering is often thought to be weirdly-shaped boundaries (hence the name gerrymandering - originating from a shape resembling a salamander and the name of the person (Governor Elbridge Gerry) who first introduced the term [1]). Therefore, compactness of the drawn constituencies has often been used as a measure of fairness. However, this is neither a necessary nor sufficient condition for detecting gerrymandering [2]. Sampling methods offer a viable alternative. We will use Markov Chain Monte Carlo (MCMC) to generate a range of potential constituency maps. Moves consist of swaps between neighbouring wards in different constituencies and are accepted/rejected with a Metropolis-Hastings step. We will define an energy function using ideas from statistical physics [3], where low-energy states will correspond to "better" constituency maps, because these low-energy maps will better fit a set of pre-determined characteristics (such as compactness of the map) which we want good maps to obey. Low-energy states, i.e., "good maps", are visited more frequently by our sampling algorithm. 

![gerry1]({{TiffanyVlaar.github.io}}/pics/Gerrymander.png)
<br>
We can now set up our constituencies' map in a statistical physics framework - using a few steps: <br>
1) Consider each ward to be a node in a graph structure. <br>
2) Draw connections between neighbouring wards/nodes, even if these neighbours are located in different constituencies. <br>
3) Associate each ward with the constituency it belongs to. For a two-constituency system we do this using an Ising spin model, where each ward has a spin associated with it which either points up or down, depending on which constituency it belongs to. Neighbouring wards/nodes which have the same spin will have an interaction energy. For a multiple-constituency system one can use the generalized version of the Ising model, which is called the Potts model. Each constituency has a different 'spin' or color associated with it, and wards assume the color/spin of the constituency they belong to. <br>
4) We define an energy function for our map, which consists of different terms that measure how well the constituency map obeys certain desirable criteria. Examples of such criteria would be compactness of each constituency and that the population of each constituency is about the same size.Lower energy maps better obey these criteria and are therefore desirable. 

Our MCMC algorithm will then work as follows:
1) Running the MCMC algorithm will change the color/spin of wards, which will affect the energy of the newly created constituency map.  <br>
2) We accept a proposed MCMC move, i.e., a move of a ward to a neighbouring constituency, with a Metropolis-Hastings step. If the move resulted in a map with a lower energy than the previous map, the move is more likely to be accepted. It is however important to also sometimes allow increases in energy to prevent the algorithm from getting stuck in local minima.



And that's it! I intend to publish more blogposts on this topic in the near future - so stay tuned!


 [1] Griffith, E. (1907). The Rise and Development of the Gerrymander, Chicago: Scott, Foresman and Co.

[2] Young, H. (1988). Measuring the Compactness of Legislative Districts. Legislative Studies Quarterly, 13(1), pp.105-115.

[3] Chou, C. and Li, S. (2006). Taming the Gerrymander—Statistical physics approach to Political Districting Problem. Physica A: Statistical Mechanics and its Applications, 369(2), pp.799-808.

