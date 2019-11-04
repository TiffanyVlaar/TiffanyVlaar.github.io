---
layout: post
title:  "Gerrymandering - Study Fairness of Political Redistricting using MCMC"
date:   2019-09-18 
categories: jekyll update
---

<!--- Redrawn Constituency Boundaries using Sampling Methods -->
***What is gerrymandering?*** <br>
Consider a two-party state X where 30% of voters vote for blue and 70% of voters vote for red. You'd expect that X's elected representatives would therefore be 30% blue and 70% red. But this is not the case in X. Instead, 60% of X's representatives are blue, and 40% are red.

This is because in 2010, blue gerrymandered X. That is to say, blue redrew X's electoral district boundaries to their advantage - they minimised the amount of "wasted" votes for their own party and maximised the amount of wasted votes for their opponents. 
<!---Gerrymandering is a term originating from US politics and involves the redrawing of constituency/electoral district boundaries to the benefit of a specific political party. Rule one of gerrymandering is to 
	maximise the amount of "wasted votes" of your opposing political party, while minimising the amount for your own party. -->
We consider votes for blue to be wasted in districts where blue lost, because these votes could instead have been used to tip a closer election in blue's favour in a neighbouring swing district. Similarly, in a district where blue won, a significant surplus in votes for blue are also wasted votes -- a district only gets one representative for state X, which will be from the winning party regardless of whether this party received 80% of the votes or 55% of the votes in this district. These surplus votes would have been better spent elsewhere. 

To illustrate this, consider the pictures below.

![gerry1]({{TiffanyVlaar.github.io}}/pics/gerry1.png)
![gerry2]({{TiffanyVlaar.github.io}}/pics/gerry2.png)

Each square block represents an equal number of voters, who all vote for the party of their colour. The rectangle represents the state that these voters live in. Suppose that the state must be divided into 3 districts with equal population, where each district holds a winner-take-all election to establish a representative. A straightforward drawing of state lines, as illustrated in the first figure, results in 1 red district, 1 blue district, and 1 tie. However, blue has more votes than it needs in the middle district. In the second figure the district boundaries have been manipulated for the advantage of the blue party, in such a way that the number of "wasted" votes for blue has been minimised. Thus we can obtain 2 blue districts and 1 tie, with the exact same votes.

<!---In the pictures above I've given an example of the effect of gerrymandering for a two-party system with three constituencies. In the United Kingdom each constituency consists of a collection of wards (the individually coloured squares). These wards are used for local government, whereas each constituency as a whole will select a single MP (member of parliament) to represent the region on a national level. In the first figure, blue has a lot of surplus votes in the middle constituency, which can be moved to neighbouring constituencies to win the election there. In the second figure the boundaries have been manipulated for the advantage of the blue party, which has now won two constituencies instead of just one. The amount of wasted votes of the red party has been maximised.
 
In practice, the gerrymandering people will do this by identifying areas where they are very unlikely or very likely to win based on historical voting data and by identifying the voting patterns of different population groups. For example, in the USA african americans typically tend to vote for the democrats. By spreading out the votes of african americans over different constituencies, republicans can manage to dissolve the influence of these votes and increase the amount of wasted votes of the democratic party.-->

So now that we understand how gerrymandering works, how can we detect if a state has been gerrymandered? A commonly thought characteristic for gerrymandering is weirdly-shaped district boundaries (hence the name gerrymandering - originating from a shape resembling a salamander and the name of the person (Governor Elbridge Gerry) who first introduced the term [1]). Therefore, compactness of the drawn districts has often been used as a measure of fairness. However, this is neither a necessary nor sufficient condition for detecting gerrymandering [2]. Sampling methods offer a viable alternative. 

***Using MCMC to study gerrymandering*** <br>
I will use Markov Chain Monte Carlo (MCMC) to generate a range of potential district maps. Moves consist of swaps between neighbouring blocks in different districts and are accepted/rejected with a Metropolis-Hastings step. I will define an energy function using ideas from statistical physics [3], where low-energy states will correspond to "better" district maps, because these low-energy maps will better fit a set of pre-determined characteristics (such as compactness of the map) which we want good maps to obey. Low-energy states, i.e., "good maps", are visited more frequently by our sampling algorithm. 
<!--- ![gerry1]({{TiffanyVlaar.github.io}}/pics/Gerrymander.png) -->

I can now set up our district map in a statistical physics framework - using a few steps:
<ol>
<li> Consider each block of voters to be a node in a graph structure. </li>
<li> Draw connections between neighbouring nodes, even if these neighbours are located in different districts. </li>
<li> Associate each node with the district it belongs to. For a two-district system we do this using an Ising spin model, where each node has a spin associated with it which either points up or down, depending on which district belongs to. Neighbouring nodes which have the same spin will have an interaction energy. For a multiple-district system one can use the generalized version of the Ising model, which is called the Potts model. Each district has a different 'spin' or color associated with it, and nodes assume the color/spin of the district they belong to. </li>
<li> I define an energy function for the map, which consists of different terms that measure how well the district map obeys certain desirable criteria. Examples of such criteria would be compactness of each district and that the population of each district is about the same size. Lower energy maps better obey these criteria and are therefore desirable. </li>
</ol>

Our MCMC algorithm will then work as follows:
<ol>
<li> Running the MCMC algorithm will change the color/spin of nodes, which will affect the energy of the newly created district map. </li>
<li> We accept a proposed MCMC move, i.e., a move of a node to a neighbouring district, with a Metropolis-Hastings step. If the move resulted in a map with a lower energy than the previous map, the move is more likely to be accepted. It is however important to also sometimes allow increases in energy to prevent the algorithm from getting stuck in local minima. </li>
</ol>



<!---And that's it! I intend to publish more blogposts on this topic in the near future - so stay tuned!-->
***References*** <br>
[1] E. Griffith. The Rise and Development of the Gerrymander. Chicago: Scott, Foresman and Co, 1907.

[2] H. Young. Measuring the Compactness of Legislative Districts. Legislative Studies Quarterly, 13(1):105-115, 1988.

[3] C. Chou and S. Li. Taming the Gerrymander—Statistical physics approach to Political Districting Problem. Physica A: Statistical Mechanics and its Applications, 369(2):799-808, 2006.

