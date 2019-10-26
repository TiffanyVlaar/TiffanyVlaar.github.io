## What is gerrymandering?
X is a state where 30% of voters vote blue and 70% of voters vote red. You'd expect that X's elected representatives would be 30% blue and 70% red. But this is not the case in X. Instead, 60% of X's representatives are blue, and 40% are red.

This is because in 2010, the blue party gerrymandered X. That is to say, blue redrew X's electoral district boundaries maps to its advantage in order to minimise their "wasted" votes and maximise that of their opponents. 

In this setting, votes for a party in a district X loses are wasted because those votes could instead have been used to tip a closer election in X's favour in a neighbouring swing constituency. Similarly, votes in excess of what party X needs in order to carry a district are wasted --a district gets one representative for X, regardless of whether it voted for X by a 51% or 91% margin. The surplus 40% of votes would have been better spent elsewhere.

To illustrate this, consider the diagram below. 

![gerry1]({{TiffanyVlaar.github.io}}/pics/gerry1.png)
![gerry2]({{TiffanyVlaar.github.io}}/pics/gerry2.png)

Each square block represents an equal number of voters, who all vote for the party of their colour. The rectangle represents the state that these voters live in. Suppose that the state must be divided into 3 districts with equal population, where each district holds a winner-take-all election to establish a representative. A straightforward drawing of state lines, as illustrated in the first figure, results in 1 red district, 1 blue district, and 1 tie. However, blue has more votes than it needs in the middle district. Manipulating the map to reduce the number of these "wasted" votes, as in the second figure, results in 2 blue districts and 1 tie. 

It was easy enough to gerrymander the toy example by hand. However, gerrymandering real-life maps is a much harder problem, and requires more sophisticated mathematics.

## Using MCMC to gerrymander

I use Markov Chain Monte Carlo (MCMC) to generate a range of potential constituency maps. Moves consist of swaps between neighbouring blocks in different districts and are accepted/rejected with a Metropolis-Hastings step. I define an energy function using ideas from statistical physics [3], where low-energy states will correspond to "better" constituency maps, because these low-energy maps will better fit a set of pre-determined characteristics which we want good maps to optimise for (e.g. wasting votes for the opposing party, district compactness so that each district looks plausible, etc). Low-energy states, i.e., "good maps", are visited more frequently by our sampling algorithm. 

We can now set up our constituencies' map in a statistical physics framework - using a few steps: <br>
1) Consider each block to be a node in a graph structure. <br>
2) Draw connections between neighbouring nodes, even if these neighbours are located in different districts. <br>
3) Associate each node with the constituency it belongs to. For a two-constituency system I do this using an Ising spin model, where each node has a spin associated with it which either points up or down, depending on which constituency it belongs to. Neighbouring nodes which have the same spin will have an interaction energy. For a multiple-constituency system one can use the generalised version of the Ising model, which is called the Potts model. Each constituency has a different 'spin' or colour associated with it, and nodes assume the colour/spin of the constituency they belong to. <br>
4) I define an energy function for our map, which consists of different terms that measure how well the constituency map obeys certain desirable criteria. Examples of such criteria would be compactness of each constituency and that the population of each constituency is about the same size. Lower energy maps better obey these criteria and are therefore desirable. 

The algorithm then works as follows:
1) Running the MCMC algorithm will change the colour/spin of a node, which will affect the energy of the newly created constituency map.  <br>
2) We accept a proposed MCMC move, i.e., a move of a ward to a neighbouring constituency, with a Metropolis-Hastings step. If the move resulted in a map with a lower energy than the previous map, the move is more likely to be accepted. It is however important to also sometimes allow increases in energy to prevent the algorithm from getting stuck in local minima.



And that's it! I intend to publish more blogposts on this topic in the near future - so stay tuned!


 [1] Griffith, E. (1907). The Rise and Development of the Gerrymander, Chicago: Scott, Foresman and Co.

[2] Young, H. (1988). Measuring the Compactness of Legislative Districts. Legislative Studies Quarterly, 13(1), pp.105-115.

[3] Chou, C. and Li, S. (2006). Taming the Gerrymander—Statistical physics approach to Political Districting Problem. Physica A: Statistical Mechanics and its Applications, 369(2), pp.799-808.
