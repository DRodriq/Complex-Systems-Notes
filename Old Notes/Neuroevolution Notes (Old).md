Neuroevolution

- Problem Types
Fractured Problems, (Kohl and Mikkulainen 2009)

- Uncategorized 
Cliff et all 1993
Nolfi and Floreano 2000
Doncieux et al 2015

- Genetic Algorithms
De Jong 1975
Goldberg 1989

- Evolution Strategies
Simple
CMA-ES
Natural Evolution Strategies
Williams REINFORCE 1992, expanded on in PEPG 2009 and Natrual Evolution Strategies 2014 - all saved on drive
OpenAI-ES, special case of REINFORCE-ES

- Textbooks
Haykin, NN: A Comprhensive Foundation (1994)
Introduction to Machine Learining

- Applications
Music Composition (Chen 2001)
Go (Richards, eta al 1998)
Robot Arm (D'Silva 2009)
Multiple Agents in Mobile ad-hoc Networks (Knoester 2010) (David B. Knoester, Heather Goldsby, Philip K. McKinley)
Multi-Agent Reinforcement Learning
Perception
NLP / LLM

- Reading List
Buckland 2002 - AI Techniques for Game Programming
Kohl 2009 - Learning in fractured problems... 
Computational Creativity (Boden 2006)
Open-Ended Evolution (Standish 2003, Bedau 2008)
Growing Adaptive Machines by D'Ambrosio (2014)

- Approaches
NEAT, Stanley and Mikkkulainen 2002
HyperNEAT, Stanley, et al 2009
RBF-NEAT
CascadeNEAT
SNAP-NEAT = Cascade + RBF
Novelty Search (Lehman and Stanley 2008,2011a)
NEAT-based methods are categorized based on 
Genetic Programming
Differential Evolution
Grammatical Evolution
Evolutionary Programming

- Implementations
SharpNEAT (C#) Green, 2004

- Companies / Groups
InstaDeep
BioNTech
Nvidia
Google DeepMind
Google Brain
OpenAI
Imperial College of Longon Adaptive and Intelligent Robotics Lab
Ecole Polytechnique Ferale de Lausanne Laboratory of Intelligent Systems- Switzerland
Naturally Inspired Computation Research Group
Institute for Experiential Robotics, Northeastern University
University Penn GRASP Laboratory
Entos, Inc (now Iambic)
Neural Propulsion systems, inc
Quebec Artificial Intelligence Institute
Learning in Machines & Brains CIFAR
Robot Perception and Learning Lab at UT Austin and Human Centerered Robotics Lab

- Journals and Blogs
Evolutionary Intelligence
Evolutionary Computation
Journal of Machine Learning Research
NeurIPS
Nature Machine Intelligence

- People
Reisinger and Miikkulainen
Yamauchi and Beer
Blynel and Floreano
Edgar Galvan and Peter Mooney
Floreano et al and Yao
Stanley
Darwish
Anima Anandkumar
Yoshua Bengio and Geoffey Hinton
Chaowei Xiao (University of Wisconsin, Madison)
Yuke Zhu (Department of CS at University of Texas Austin)

- Gene Representations
Indirect, Direct, Implicit Encodings

- Dynamic Neuron Models
Continous-Time Recurrent Neural Networks - Universal Dynamic Approximators

- Benchmarks and Environments 
MNIST
Double Pole Balancing
Gym
Roboschool
PyBullet

- Interesecting Areas
Image Processing
Deep Reinforcement Learning
Mult-Agent Learning
Meta-Learning

- Problems in NE
Competing Conventions Problem - (Montana and Davis 1989, Shaffer 1992)
	- Having more than one way to express a solution, different encodings, leading to damaged offspring

- Timeline
1795 Gauss, 1805 Legendre, use method of least squares or linear regression for prediction of planetary movement
1925 Ising Model created
1949 Warren Mcculloch and Walter Pitts wrote a paper on how neurons might work
1949 Donald Hebb wrote "The Organization of Behavior", introduced Hebbian Learning
1952 Arthur Samuel coined the term Machine Learning. His work included alpha-beta pruing and the minimax algorithm
1959 Frank Rosenblatt combined Hebb's brain cell model with Arthur Samuel's ML and created the perceptron
1960 Henry J. Kelley and Arthur E. Bryson used princples of dynamic programming to derive method listed below
1962 Term "back-propogating error correction" introduced by Frank Rosenblatt. Precursor implemented by Henry J. Kelley in context of control theory 
1962 Stuart Dreyfus published simpler derivation of backprop based only on chain rule applied to networks of differentiable nodes
1965 Nilsson's "Learning Machines: Foundations of Trainable Pattern-Classifying Systems" published
1965 First deep learning MLP published by Ivakhnenko and Lapa
1967 Nearest Neighbor Algorithm, beginning basic pattern recognition
1969 Kunihiko Fukushima introduced ReLU activation function
1967 First deep learning multilayer perceptron trained by stochastic gradient descent published by Shun'ichi Amari
1972 Kohonen and Anderson independently developed a network utilizing matrix mathematics
1970s ML mostly interest in pattern recognition (Duda and Hart 1973)
1975 First multilayered NN developed
1980 CNNs introduced by Kunihiko Fukushima
1982 Paul Werbos applied backprop to MLPs in a way that became standard
1982 SOMs published by Teuvo Kohonen
1986 Rumelhart, Hinton, Williams showed backprop learned internal representations of words as feature vectores when trained
1987 TDNN introduced by Alex Waibel combining convolutions and weight sharing and backprop
1988 Wei Zhang applied backprop to a CNN
1988 NNs applied to protein structure prediction
1990 Boosting concept introduced by Robert Schapire in "The Strength of Weak Learnability"
1991 Juergen Schmidhuber published adversarial neural networks
1991 Sepp Hochreuter published his thesis identifying and analyzing the vanishing gradient problem and proposed recurrent residual connections solution
1992 Max-Pooling for CNNs was introduced by Juan Weng to help with least-shift invariance
1992 Juergen Schmidhuber proposed a hierarchy of RNNs pretrained one level at a time with self-supervised learning to overcome backpropogation's limititations on FNNs and RNNs. The RNN hierarchy can be collapsed into a single RNN, by distilling a higher level chunker network into a lower level automatizer network
1992 Juergen Schmidhuber introduced alternative to RNNs, called a linear transformer
1997 Hochreiter's work leads to Long Short-Term Memory deep-learning method published in Neural Computation
1998 7-level CNN by Yann LeCun applied to handwritten checks 
1999 "Vanilla" LSTM introduced by Felix Gers, Schmidhuber, Fred Cummins
2002 Evolving Neural Networks Through Augmenting Topologies published by Stanley and Miikkulainen
2005 Rupesh Kumar Srivastava, Klaus Greff, and Schmidhuber used the LSTM principle to create the Highway network
2005 Kaiming He, Xiangyu Zhang; Shaoqing Ren, and Jian Sun won the ImageNet 2015 competition with an open-gated or gateless Highway network variant called Residual neural network
2007 Stanley publishes CPPN paper
2009 Stanley publishes "A hypercube-based encoding for evolving large-scale neural networks"
2009 Graves LSTM won three competitions in connected handwriting
2010 Curesan et al show that GPUs make backpropagation feasible for many-layered feedforward neural networks
2011 Abandoning objectives: Evolution through the search for novelty alone
GA's used to evolve weights of a fixed topology (1989 - 1999)
Topology Evolution (1994 - 2002)
2017 Stanley "Deep neuroevolution: Genetic algorithms are a competitive alternative for training deep neural networks for reinforcement learning"
2017 Ashish Vaswani introduced modern transformers with their paper "Attention is All You Need"
2019 Stanley "Designing neural networks through neuroevolution"
2023 Backpropogation implemented on a photonic processor by a team at Stanford

- Research Paper Common Structures
<Some Improvement / Interesting Result > using <New Technique>
<Using X Technique> for <Some Improvement / Interesting Result>
<Applying X Technique> to <Different Kind of Problem Than Normally Studied>

- Notes from Papers
{	From "Comparison of NEAT and HyperNEAT on a Strategic Decison-Making Problem"
	HyperNEAT improves upon NEAT for relatively simple fractured problems, but the benefits disappear as the problem gets more complicated. This is based on this experiment only and should be tested on other problems
	Look into "fractured problems"
	Some work has been done to extend NEAT for performance on fractured problems. Kohl and Mikk (2009) demonstrated that NEAT's performance on several fractured problems can be improved if a mutation is added to the algorithm that allows the addition of radial basisc function nodes (RBF-NEAT). Also suggests that NEATs performance could be improved if its search space were constrained to cascade architectures, a network arrchitecture in which each hidden node is connected to all hidden nodes to its left in addition to inputs and outputs (Cascade-NEAT)
	More future work would be improving implementations for computer performance
	Machine Learning Technique - Random Decision Forests for determining for themselves when they've had enough training through the use of statistical hypothesis tests
}
{	From "Quality Diversity: A New Frontier for Evolutionary Computation"
	Natural evolution isn't just perfromance optimization, it is a divergent search that optimizes locally within each niche as it simultaenously diversifies. Discovery is of both quality and diversity -> Quality Diversity (QD) Algorithms
	Novelty Search (Stanley and Lehman 2008, 2011a) has effectively shown that evolutions talent for diversification can itself be harnessed as a powerful tool for seeking a near-optimum.
	Quaity Diversity seeks to find a maximally diverse collection of individuals in which each member is as high performing as possible. One algorithm is Novelty Search with Local Competition (Lehman and Stanley 2011b) and MAP-Elites (Mouret and Clune 2015)
	In QD, diversity between individuals is measured with respect to behavior, from which an experimenter selects some subset of behavioral features of interest to form a behavior characterization. These behavior spaces must be divided into niches that together cover the entire space.
	Mouret and Clune 2015 - QD effectively reveals the best possible performance achievable in each region of the phenotype space
}
{ From "A Systematic Literature Review of the Successors of “NeuroEvolution of Augmenting Topologies"
	NEAT-based methods are categorized based on 
		1. Whether they consider issues specific to the search space or fitness landscape
		2. Whether they combine principles from NE and another domain or
		3. The particular properties of the evolved ANNs
}
{	From "A Systematic Comparison of Simulation Software for ..."
	A recent example of a digital twin solution for a robotic
	arm can be found in [8] where the authors used ROS to achieve seamless operation between
	the real and digital world
	From our review and experimental results, we found
	that current robot simulation software could not be used
	to develop a digital twin. This is because the simulators
	considered in this paper cannot maintain a repeatable simulated scene over time. We hypothesise that a continuous
	feedback mechanism is needed between the simulation and
	reality similar to [22] in order to maintain an accurate
	representation of the real environment -> 22: “Sim2Real2Sim: Bridging the Gap Between Simulation and Real-World in Flexible Object Manipulation
}
{	From "Neuroevolution Through Augmenting Topologies"
	- Many systems have been developed over the last decade that evolve both neural network topologies and weights (Angeline et al., 1993; Braun and Weisbrod, 1993; Dasgupta and McGregor, 1992; Fullmer and Miikkulainen, 1992; Gruau et al., 1996; Krishnan and Ciesielski, 1994; Lee and Kim, 1996; Mandischer, 1993; Maniezzo, 1994; Opitz
	and Shavlik, 1997; Pujol and Poli, 1998; Yao and Liu, 1996; Zhang and Muhlenbein, ¨1993)
	- TWEANNs can be divided between those that use a direct encoding, and those that
	use an indirect one. Direct encoding schemes, employed by most TWEANNs, specify
	in the genome every connection and node that will appear in the phenotype (Angeline et al., 1993; Braun and Weisbrod, 1993; Dasgupta and McGregor, 1992; Fullmer and Miikkulainen, 1992; Krishnan and Ciesielski, 1994; Lee and Kim, 1996; Maniezzo,
	1994; Opitz and Shavlik, 1997; Pujol and Poli, 1998; Yao and Liu, 1996; Zhang and
	Muhlenbein, 1993). In contrast, indirect encodings usually only specify rules for con- ¨
	structing a phenotype (Gruau, 1993; Mandischer, 1993).
	- Subgraph swapping is representative of a prevailing philosophy in TWEANNs that subgraphs are functional units and therefore swapping them
	makes sense because it preserves the structure of functional components
	- Several different problems with TWEANNs
}
{	From "Efficient Reinforcement Learning through Evolving Neural Network Topologies"
	- As of 2002, NE methods were the strongest method on the pole-balancing benchmark RL tasks, but evolving topology was not yet done much. 
	- NEAT is introduced focused on principled crossover, protection of structural innovation, and using incremental growth from minimal structure
	- NEAT, and NE generally is a way of learning with sparse reinforcement
	- Pole-balancing NE results were gained from evolving weights on fixed topologies
	- An open question then (answered now?) is whether Topology evolution can enhance performance, and if so if its worth the tradeoff of increased difficulty
	- Topology evolving method called Cellular encoding (Gruau 1996) was compared to ESP (Gomez and Miikulainen 1999). ESP was 5 times faster even tho it uses a random number of hidden nodes
	- NEAT's genetic encoding is nothing special other than its innovation number. It uses connection and node genes, with mutation occuring on the weights and addition of nodes. 
	
}

NEAT Framework
(1) Is there a genetic representation that allows
disparate topologies to crossover in a meaningful way? 
(2) How can topological innovation that needs a few generations to optimize be protected so that it does not disappear
from the population prematurely? 
(3) How can topologies be minimized throughout evolution without the need for a
specially contrived fitness function that measures complexity?

What if? :
+ Instead of tracking genes through historical markings and the innovation number, any gene can be tagged as a line up point, and what genes are or are not tagged is a part of speciation 
- When species reproduce, they will produce several candidate zygotes. Most will have inherited number of line up points, but some will have one extra, one less, or a shifted one. 
- If the reproducing agents have contributed any zygotes with the same # of lineup points, they will each contribute a zygote for crossover. Therefore speciation is defined by number of lineup points
+ There were some weight training / learning method applied on agents during their lifespan
- Some percentage of the difference between their natural weight and the end learned weight were applied to offspring
- When weights on a connection are decreased enough, the connection is killed. 
- When weights on a connection are increased enough, the connection splits into two neurons

- Elements of a Framework
Fixed morphology. Fixed features. Fixed set of inputs and outputs. How to create an environment with a rich or implict set of inputs and outputs?
	- Implicit caloric need based on brain complexity, how often they compute
	- Lifespan is based on 
	- Invest time or resources into elements that alter the environment
		- Lay down pheromone trails that can only be read by their own species
		- "Nests" that decrease reproduction after an initial investment
		- Selectively target species to cultivate / farm other species
	- Certain species will gravitate towards doing different things
Implicit energy usage / complexity score
Genomic representation of NN, can I evolve an encoding scheme?
Representation of input and output data to the cortex
Online learning, including learning implementations/strategies that can also evolve
Speciation. What about two genomes is sufficient or necessary for the ability to crossover
Sexual crossover of two genomes - how to

Ideally, I want every component of this to evolve.