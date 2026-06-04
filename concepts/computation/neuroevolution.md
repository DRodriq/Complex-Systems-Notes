---
type: concept
domain: computation
related_domains: [complexity]
provenance: mixed
status: developing
relates_to:
  - target: genetic-algorithms
    relation: extends
  - target: neural-networks
    relation: overlaps
  - target: quality-diversity
    relation: overlaps
  - target: concepts/complexity/fitness-landscapes
    relation: used-in
tags: [neuroevolution, NEAT, evolutionary-computation, architecture-search, gradient-free]
---

# Neuroevolution

> Evolving neural network weights, architectures, or both using evolutionary algorithms rather than gradient descent — enabling gradient-free optimization, open-ended architecture search, and adaptation in non-differentiable settings.

## Orientation

Neuroevolution sits at the intersection of evolutionary computation and deep learning. It asks: instead of training neural networks by backpropagation, can we evolve them? The answer is yes, with tradeoffs — neuroevolution is gradient-free (applicable where gradients are unavailable or misleading) and can search the space of architectures (not just weights), but is generally less sample-efficient than gradient-based methods for well-behaved problems.

For this vault, neuroevolution is significant because it embodies the adaptation mechanism in the computation domain — it is Holland's GA applied to the problem of finding good neural network structures.

## Core

### Why Evolve Networks?

Gradient descent requires differentiability — the loss must be a smooth function of the weights. Many interesting problems violate this: sparse reward RL environments where the gradient signal is absent for long stretches, combinatorial architecture choices (number of layers, connections, activation functions), and settings where the objective is complex or non-stationary.

Neuroevolution addresses all three. It treats the network (weights or structure) as the genotype, fitness (task performance) as the objective, and applies selection and variation. No gradients needed.

### NEAT: Neuroevolution of Augmenting Topologies

Stanley and Miikkulainen's NEAT (2002) is the most influential neuroevolution algorithm. The key innovation is evolving both the weights and the topology of networks simultaneously, starting from minimal networks and growing complexity only as needed.

NEAT addresses two problems that prior neuroevolution faced:

**The competing conventions problem**: When two networks have the same function but different topologies, crossover between them produces incoherent offspring. NEAT uses historical markings (innovation numbers) to align genes from different topologies before crossover.

**The problem of innovation**: New structural innovations (adding a node or connection) start with low fitness because their contribution is not yet refined. NEAT uses speciation — protecting innovations by keeping them in separate species, giving them time to optimize before competing with established solutions.

Results: NEAT could solve problems that fixed-topology neuroevolution could not, including the classic double-pole balancing problem without velocity information, which requires evolving a recurrent connection.

### Modern Variants

**HyperNEAT** extends NEAT using compositional pattern-producing networks (CPPNs) to encode connectivity patterns geometrically — useful for large networks where direct encoding is impractical.

**ES (Evolution Strategies)** — OpenAI's ES (2017) shows that simple Gaussian perturbation of weights with fitness-based selection, parallelized across many workers, can compete with RL algorithms on benchmark tasks. Not quite neuroevolution in the structural sense, but demonstrates the practical viability of gradient-free neural optimization.

**Quality-Diversity algorithms** (MAP-Elites, AURORA) extend the evolutionary framework to search for diverse repertoires of behaviors rather than a single optimal solution. See `concepts/computation/quality-diversity.md`.

### Relationship to Neural Architecture Search

Neural architecture search (NAS) is the modern machine learning framing of the same problem: searching the space of network architectures for ones that perform well on a target task. Early NAS used evolutionary algorithms (as in neuroevolution). Most modern NAS uses differentiable methods (DARTS) or reinforcement learning to guide the search more efficiently, trading the generality of evolutionary search for sample efficiency.

## Connections

**Genetic algorithms** (`concepts/computation/genetic-algorithms.md`) — neuroevolution applies GA logic to neural networks; NEAT is a GA with structured crossover for variable-topology graphs.

**Neural networks** (`concepts/computation/neural-networks.md`) — the substrate being evolved; neuroevolution and backpropagation are alternative optimization strategies for the same class of models.

**Quality diversity** (`concepts/computation/quality-diversity.md`) — evolutionary algorithms that optimize for both performance and behavioral diversity; extends neuroevolution toward open-ended exploration.

**Fitness landscapes** (`concepts/complexity/fitness-landscapes.md`) — the weight and architecture space defines a fitness landscape; neuroevolution searches it evolutionarily.

**Adaptation thread** (`synthesis/adaptation-thread.md`) — neuroevolution is the clearest instantiation of the adaptation mechanism in modern machine learning.

## Sources

- `sources/papers/stanley-miikkulainen-neat-2002.md`

## Open Questions

- When is neuroevolution genuinely competitive with gradient-based methods, and when is it only applicable as a fallback when gradients are unavailable?
- Can architecture search be made as principled as the schema theorem makes genetic algorithm search — is there a theory of what makes a network architecture "evolvable"?
- Do quality-diversity neuroevolution methods produce more robust solutions than single-objective optimization, and at what cost in specialization?
