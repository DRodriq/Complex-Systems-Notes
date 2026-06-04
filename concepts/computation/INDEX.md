---
type: domain-index
domain: computation
status: developing
---

# Computation Domain

> The study of information processing in natural and artificial systems — including how neural networks learn, how evolutionary algorithms search, how cellular automata compute, and how the architecture of modern large language models relates to the broader computational theory of mind and complex systems.

## What This Domain Covers

This domain spans two related but distinct areas. The first is the classical AI and machine learning lineage: from early expert systems through connectionism (neural networks), through deep learning, to the transformer architectures that underpin modern LLMs. The second is the complexity-theoretic framing of computation: cellular automata, genetic algorithms, the edge of chaos hypothesis, and the question of whether biological and social systems perform computation in a meaningful sense.

These two areas are increasingly convergent. Neural networks interpreted as dynamical systems, the edge-of-chaos training hypothesis, and neuroevolution all sit at the boundary.

## Core Concepts

| Concept | One-line description | Status |
|---|---|---|
| [[neural-networks]] | Parameterized function approximators built from layered linear transformations and nonlinearities; trained by backpropagation | developing |
| [[transformers-and-attention]] | The architecture underlying modern LLMs; replaces recurrence with self-attention over full sequences | developing |
| [[genetic-algorithms]] | Holland's evolutionary search method: populations, selection, crossover, mutation | developing |
| [[cellular-automata]] | Discrete dynamical systems on grids; Wolfram's program for finding computation in simple rules | developing |
| [[neuroevolution]] | Evolving neural network architectures and weights using evolutionary algorithms rather than gradient descent | developing |
| [[reinforcement-learning]] | Learning by reward signal from environment interaction; connects to CAS and adaptation | developing |
| [[multi-agent-rl]] | Multiple learning agents interacting; the RL framing of CAS | developing |
| [[quality-diversity]] | Optimization for both performance and behavioral diversity; illumination algorithms | developing |
| [[edge-of-chaos]] | The hypothesis that maximal computational capacity lives at the phase transition between order and chaos — see concepts/complexity/edge-of-chaos.md | developing |
| [[umap]] | Dimensionality reduction via Riemannian manifold approximation; grounded in algebraic topology | stub |

## Connections to Other Domains

- **Dynamics**: Neural networks are dynamical systems. Their training dynamics, representational geometry, and generalization can be analyzed with dynamical systems tools. The edge of chaos is a dynamics concept applied to computation.
- **Complexity**: Genetic algorithms are the computational formalization of adaptation — the core CAS mechanism. Cellular automata are the simplest model systems for studying emergence in computation.
- **Information**: All computation is information processing. Shannon entropy, Kolmogorov complexity, and effective complexity all have computational interpretations.
- **Networks**: The architecture of neural networks is a directed graph. Attention mechanisms implement a form of dynamic, learned network topology over input sequences.

## Key Figures

[[John Holland]] · [[Kenneth Stanley]] · [[Risto Miikkulainen]] · [[Antoine Cully]] · [[Christopher Langton]] · [[Stephen Wolfram]] · [[Eli Shlizerman]]

## Key Sources

- `sources/papers/stanley-miikkulainen-neat-2002.md` — NEAT: neuroevolution of augmenting topologies
- `sources/papers/edge-of-chaos-nn-training-2021.md` — edge of chaos as guiding principle for NN training
- `sources/papers/cully-quality-diversity-2017.md` — quality diversity optimization framework
- `sources/papers/nn-as-dynamical-system-shlizerman-2023.md` — neural networks as a new type of dynamical system
