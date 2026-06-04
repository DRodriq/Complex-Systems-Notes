
1. (Methodology, Implementation) Modeling predator and prey dynamics using networks

Each agent is modeled as a multi-node - with each property of an being represented as a node on the network of property or properties being represented.
Interactions between agents are represented as edges between shared or related properties. 

For instance, all agents will have the location property, which they share as a link on the location network if they are in the same location (binary, undirected network)
Another example, agents with the 'prey' property will share an edge with agents of the 'predator' property. A super network would combine both these networks and each edge would be a computation - say in the case of the intersection of predator/prey at a location the chance of prey being hunted.


2. Information Flow in Peer Cooperative Networks
Several agents communicate independently with a central server. 
Agents are using state variables from the server to try and predict the trajectory of the systems evolution. The server is simulating a system of some complexity (periodicity, chaos level, something)
The agents all have access to input vectors and attempt to predict the next state, and then compare their prediction to the actual result
Agents also see the predictions of other agents and can compare peer accuracy to their own

Questions: 
How does the amount of information that can flow from one peer to another impact performance of the agents in approximating the system? Are there tradeoffs between how informational schemes will impact the distribution of agent performance - say one method of information sharing results in a rich get richer phenemenon or another results in more egalatarian performance across agents? 


3. Exploring an infinite domain space with limited trajectories available for travelling
Imagine an unbounded multi-dimensional space 
Is there a finite number of trajectories (transition deltas from state at time t to time t+1) that allow traversal of the entire domain. Basically, can we explore an entire space with only a few modes of manipulation available to us, and how to prove this yes or no?


4. Limits of information / predictive ability and its relationship to diversiy, evolution, novel behavior
A complex system is balancing emergence with self-organization, or from another view balancing order and chaos. What is the relationship between the limits of the information available to agents and the diversity, evolution, extinction rates? How does information / predictive capability measure with the space of possibile strategies/evolution and the observed exploration of that possible space? 

How to experiment this: 
Say we have a population of simple starting agents in a dynamic enviornmnet. Multiple strategies should be viable, and multiple adaptions available to the agents for exploring and refining these strategies. If we can measure the information content in the agent-env system and get a measure of the stability/chaotic-ness and measure the information available to agents, can we compare these relative informational contents to how evolving agents explore the possible solution space?


5. Cost/benefit (tradeoff) of strategic adaptations and complexity
Open question to how the relation of cost/benefit tradeoffs to adaptations relate to or reflect the complexity of an agent-env system. Faster movement speed at the expense of greater metbolic rate would be one example that reveals much about the nature of the system. Considering the overlaps of multiple of these cost/benefit adaptations could reveal or define a possible solution/possibility space, and the dynamics of how these tradeoffs evolve would be interesting to study. On that last point, agents successfully evolving to move faster at the expense of faster metabolic rate would shift the entire solution space and cost benefit analysis for the rest of the agents. 