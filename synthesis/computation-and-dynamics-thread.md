---
type: synthesis
domain: computation
related_domains: [dynamics, complexity, information]
provenance: synthesis
status: developing
relates_to:
  - target: concepts/dynamics/chaos-theory
    relation: foundation-for
  - target: concepts/computation/cellular-automata
    relation: extends
  - target: concepts/computation/neural-networks
    relation: extends
  - target: concepts/computation/transformers-and-attention
    relation: extends
  - target: concepts/complexity/edge-of-chaos
    relation: foundation-for
---

# Computation and Dynamics Thread

*This document traces a thread the vault author identifies as running from cellular automata through the edge-of-chaos hypothesis to neural networks as dynamical systems and into the architectural questions raised by modern LLMs. The connections here are interpretive — this is one way to read the relationship between computation theory and dynamical systems. The thread is real and documented in the literature, but the framing of it as a unified intellectual arc is synthesis.*

## Orientation

The deepest question this thread addresses is: what is the relationship between computation — in the abstract, theoretical sense — and physical dynamics? At one end sits the Church-Turing thesis, which says computation is substrate-independent, an abstract mathematical object. At the other sits the intuition, developed through complexity science, that computation is something physical systems actually *do* — that it emerges from dynamics in the same way that order, life, and intelligence do. The thread runs from Wolfram and Langton's cellular automata work in the 1980s, through the edge-of-chaos hypothesis, through reservoir computing, to the modern question of what neural network architectures are doing when they compute.

The thread is not a settled story. It is a set of convergences that suggest computation and dynamics are more deeply related than the standard computer science framing acknowledges, without yet producing a unified theory.

## The Cellular Automaton as Model System

The thread starts with the cellular automaton — a grid of cells, each updating its state according to a fixed local rule based on its neighbors. No moving parts, no memory, no centralized control. Wolfram systematically explored the space of one-dimensional CA rules in the early 1980s and found that they fell into four behavioral classes:

- **Class I**: All cells converge to a fixed state. Ordered, dead.
- **Class II**: Periodic patterns. Structured but static.
- **Class III**: Chaotic, disordered behavior. No stable structure.
- **Class IV**: Complex, persistent structures that propagate and interact. Neither ordered nor chaotic.

Class IV is where computation lives. Wolfram showed that Rule 110, a Class IV automaton, is Turing-complete — capable of universal computation given appropriate initial conditions. The implication is stark: the capacity for universal computation is not a property that has to be engineered in. It can arise spontaneously in a system governed by a simple local rule, provided that rule produces Class IV dynamics.

Langton formalized this into a quantitative framework using the *lambda parameter* — a single number measuring the fraction of non-quiescent transitions in a CA rule table. As lambda increases from 0 to 1, CAs move from Class I/II behavior through Class IV and into Class III chaos. The transition between Class II and Class III — the edge between order and chaos — is where Class IV complexity concentrates. This is the first statement of the edge-of-chaos hypothesis: complex behavior, and with it the capacity for computation, emerges at a phase transition.

See `concepts/computation/cellular-automata.md` and `concepts/complexity/edge-of-chaos.md`.

## Edge of Chaos as Computational Hypothesis

Langton's hypothesis was not just about cellular automata. The claim was general: *systems at the edge between ordered and chaotic dynamics have maximal capacity for computation and information processing.* Order is too rigid to support complex information processing — the system cannot change state in response to inputs in a rich enough way. Chaos is too fluid — information is generated faster than it can be used. The critical regime between them is where both structure and flexibility coexist.

This was extended by Kauffman from a different direction. His NK model of genetic regulatory networks showed that networks with moderate connectivity K (neither too sparse nor too dense) sit at a phase transition between ordered and chaotic dynamics, and that this regime is where evolution is most effective. Biological organisms, on this view, have been selected to sit near criticality — not because criticality is optimal for any single task, but because it is optimal for adaptive search in a changing environment.

Packard's work suggested that evolution in cellular automata specifically selected for lambda values near the critical transition. If true, this means that evolution finds the edge of chaos not because it is seeking it but because that is where complex adaptive behavior lives.

The edge-of-chaos hypothesis is empirically contested. It is hard to define "criticality" precisely enough to test across substrates, and the evidence for biological systems is mixed. But as a framing for where to look for interesting computational behavior in physical systems, it has proven generative.

See `concepts/complexity/edge-of-chaos.md` and `concepts/complexity/complex-adaptive-systems.md`.

## Neural Networks as Dynamical Systems

The thread arrives at neural networks through a shift in how they are understood. The standard framing — a neural network is a parameterized function approximator, trained by gradient descent on a loss — is useful for engineering but strips out the dynamical character of the computation.

The alternative framing: a neural network is a dynamical system. Its forward pass is a trajectory through activation space. Its training is a trajectory through weight space. The loss landscape is a high-dimensional surface, and gradient descent is flow on that surface toward local minima. The geometry of this flow — its attractors, its saddle points, its basins — determines what the network learns and how it generalizes.

This reframing is most explicit in **reservoir computing**, where a large fixed random recurrent network (the reservoir) is driven by an input signal and only the readout weights are trained. The reservoir's job is to project the input into a high-dimensional dynamical space rich enough that the readout can find linear combinations that solve the task. The reservoir computes; the training just extracts. This is a clean separation between the dynamics and the learning, and it makes the dynamical framing explicit.

**Recurrent neural networks** (RNNs, LSTMs) are dynamical systems by construction — they carry a hidden state that evolves over time according to a learned function. The LSTM's gating mechanism is specifically an architecture for controlling the flow of information through a dynamical system: deciding what to remember, what to forget, what to output. This is a designed attractor structure.

The connection to the edge of chaos appears in training dynamics. A network whose Jacobian has all eigenvalues inside the unit circle is contracting — signals decay, gradients vanish, nothing interesting happens. A network whose Jacobian has eigenvalues outside the unit circle is expanding — signals and gradients explode. The productive training regime is near the edge: eigenvalues near the unit circle, neither decaying nor exploding. This is the vanishing/exploding gradient problem reframed as a criticality problem, and it motivates the edge-of-chaos training hypothesis in the Zhang et al. paper in this vault.

See `concepts/computation/neural-networks.md` and `sources/papers/zhang-edge-of-chaos-nn-2021.md`.

## The Transformer Break

The transformer architecture, introduced in 2017, represents a partial departure from the dynamical systems framing. The transformer does not process sequences through recurrent state — it processes entire sequences in parallel through self-attention, where every position attends to every other position simultaneously. There is no trajectory through time in the classical sense; the computation is more geometric than dynamical.

This shift has real consequences for how the computation-and-dynamics thread applies. The recurrent/reservoir framing does not transfer cleanly. The gradient flow analysis of RNNs does not directly apply to transformers, which use residual connections and layer normalization specifically to control signal propagation without enforcing the spectral constraints that recurrent networks need.

But the thread does not end here — it changes character. The transformer can be read as a dynamical system in a different sense: each layer is a transformation of a residual stream, and the sequence of layers is a discrete-time trajectory through a high-dimensional representation space. Attention is not recurrence, but it implements a form of context-sensitive routing — each token's representation at each layer is a weighted mixture of all other tokens' representations, where the weights are learned functions of the current state. This is not classical dynamics, but it is also not purely static function composition.

Active work applies dynamical systems tools to transformers in this sense: analyzing the geometry of attention, the dimensionality and structure of residual stream trajectories, and the phase transitions in model behavior as scale increases. The question of whether large transformers are near some analog of criticality — whether their scale-driven capabilities emerge from a phase transition in the same spirit as Langton's — is open and worth tracking.

See `concepts/computation/transformers-and-attention.md`.

## The Broader Question

Behind this thread is a deeper question that has not been resolved: is computation a natural phenomenon or an engineered one?

The Church-Turing framing says computation is abstract and substrate-independent — physical systems implement it, but the mathematics is not about the physics. The complexity science framing, developed through this thread, suggests something else: that the capacity for complex computation arises from physical dynamics at critical transitions, that evolution finds it, that brains inhabit it, and that the most powerful artificial systems we build converge on something like it whether or not we design them to.

The thermodynamics of computation (Landauer, Bennett) adds another layer: computation has physical costs. Erasing a bit dissipates heat. Reversible computation could in principle be free. These results connect information processing to statistical mechanics in a way that suggests computation is not purely abstract but is genuinely constrained by physics.

Whether modern large language models fit into this picture — whether the behaviors that emerge with scale are edge-of-chaos phenomena, whether the attention mechanism is a form of the computation Langton identified in Class IV automata, whether transformers at scale are near criticality in any meaningful sense — is not known. These are the open questions at the frontier of this thread.

## Connections

**Cellular automata** (`concepts/computation/cellular-automata.md`) — the origin of the thread; where computation-in-dynamics was first observed systematically.

**Edge of chaos** (`concepts/complexity/edge-of-chaos.md`) — the hypothesis that is the thread's central claim; sits between the CA work and the neural network work.

**Chaos theory** (`concepts/dynamics/chaos-theory.md`) — the dynamical systems foundation; strange attractors and Lyapunov exponents are the tools applied to networks.

**Neural networks** (`concepts/computation/neural-networks.md`) — the contemporary endpoint of the thread in classical deep learning.

**Transformers and attention** (`concepts/computation/transformers-and-attention.md`) — where the thread becomes uncertain; the architecture that challenges the dynamical framing.

**Measuring complexity** (`synthesis/measuring-complexity-thread.md`) — Kolmogorov complexity and logical depth connect to the computational side of this thread; computation and information are the same thing viewed differently.

## Open Questions

- Is there a precise analog of Langton's lambda for neural network architectures — a single parameter that predicts proximity to a useful critical regime?
- Do large transformer models exhibit phase transitions in capability that are analogous to the order-to-chaos transitions in cellular automata and NK models?
- Is the edge-of-chaos training hypothesis (Zhang et al.) empirically robust across architectures and scales, or is it specific to certain regimes?
- What is the right dynamical framing for transformer computation, given that residual stream trajectories are not recurrent dynamics?
- Does the thermodynamics of computation (Landauer) have practical implications for the energy costs of training and running large models, or is it only relevant at much finer physical scales?
