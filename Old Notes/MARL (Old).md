Notes from MARL

The concepts of States, Actions, Observations, and Rewards are formally defined within game models

Three major categories: 
- Centralized training and execution 
- Decentralized training and execution, assumes no centrally shared information
- Centralized training with decentralized execution

Dimensions to consider:
Size - # of Agents, Environment States, Actions Available
Knowledge - What do agents know about their actions and other agents actions
Observability - What can agents observe? Are their observations noisy? Can they observe the actions/rewards of other agents?
Rewards - Do agents split rewards, share rewards etc
Objective - What is the total goal
Centralisation and Communication - Can agents coordinate their actions? Is the channel reliable, noisy, etc

Challenges
Agents may have conflicting goals, partial views of the world, and agents are learning concurrently
- Non-stationarity. Don't super understand but basically continually changing policies of agents leads to moving targets for other agents that are reacting to learn based on each other. Mathematically non-stationarity is a condition where mean, variance, or autocorrelation of a time series change over time, implying data does not have a stable or predicatble behavior. How to handle this or what it means for learning is crucial
- Optimality of policies and equilibrium selection - When are the policies of agents in a mult-agent system optimal? More sophisticated notions of optimality are needed, such as equilibrium-type solutions. 
- Multi-agent credit assignment - Temporal credit assignment in RL is the problem of determining which past actions contributed to a reward. In MARL, whose actions contributed to the award? (Who cares?) If the goal is one of a system, say a most efficient warehouse instead of a most efficient individual bot, who cares about individual credit assignment? 
- Scaling in # of Agents - The number of possible action combinations scales exponentially with the number of agents

Agendas of MARL
Shoham, Powers, and Grenager (2007) - "If multi-agent learning is the answer, what is the question?" - part of a special issue of Artificial Intelligence Journal (2007)
How does this question relate to Stanley's open-ended evolution ideas and newer Quality Diversity ideas

Book Structure:
P1: Foundational Knowledge and Concepts
	C2: Theory and Tabular Algos for Single-Agent RL
	C3: Introduces basic game models
	C4: Solution Concepts
	C5: Central and Independent Learning
	C6: Different Classes of Foundational Algos
P2: Contemporary Research in MARL Levaraging Deep Learning for Powerful MARL Algos
	C7: Intro to Deep Learning
	C8: Intro to Deep RL
	C9: Important MARL Algos
	C10: Practical Guidance
	C11: Examples of Multi-Agent Environments

C2: 
Key Terms:
RL, Markov Decision Process, Bellman Equations, Temporal-difference learning, Decision Process Models, Sequential Decision Process

General Definition of RL 
Introduction of the Markov Decision Proces
Using MDP model, define basic concepts such as expected returns, optimal policies, value functions, bellman equations.
Two basic families of algos to compute optimal policies for MDPs: dynamic programming and temporal-difference learning
Dynamic programming requires complete knowledge of the MDP, temporal-difference does not it instead it learns by interacting with the environment and generating experiences. MARL mostly builds on these temporal-difference algos and extends them to game models.
In essence, an RL Problem is the combination of a decision process model (MDP, POMDP, mult-armed bandit) and a learning objective which specifies the properties of the optimal policy to be learned
RL algos learn solutions for sequential decision processes via repeated interaction with an environment. This raises three questions:


My own thoughts 
- Start with a set of fundamental environmental resources {A,B,C,...,Z}
- Each fundamental resource has the following characteristics - Stability, Generation Rate, Metabolic Yield
	Stability is the rate of decay of a resource in the environment, how many turns it can exist
	Generation Rate is the probability each turn a resource will appear at a square
	Yield is the energy/wealth/food yield of the resource
- Agents are created that can utilize metabolics 

P=NP
Sudoku - The time to verify a solution is simple and grows polynomially as the grid gets larger. All algorithms for finding a solution take exponentially longer as the grid gets bigger. 
Agents start off being able to take the input of a grid and output a grid. If they change a number that was fixed in the input, they die. If they attempt 

Evaluating agents in a game:
Who is better/best at the game? Straightforward
Who got better faster, ie: one agent is just as good but has less experience than another agent
Who is improving at the greatest rate? ie: an agent is not very good yet but massively improved since the last run