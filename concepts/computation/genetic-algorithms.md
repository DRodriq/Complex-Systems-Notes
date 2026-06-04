---
type: concept
domain: computation
related_domains: [complexity, applied]
provenance: mixed
status: developing
relates_to:
  - target: concepts/complexity/adaptation
    relation: instance-of
  - target: concepts/complexity/fitness-landscapes
    relation: used-in
  - target: neuroevolution
    relation: foundation-for
  - target: concepts/complexity/complex-adaptive-systems
    relation: foundation-for
tags: [genetic-algorithms, Holland, evolutionary-computation, schema-theorem, optimization]
---

# Genetic Algorithms

> Holland's computational formalization of Darwinian adaptation: maintain a population of candidate solutions, evaluate fitness, select the better ones, recombine and mutate to produce the next generation. The substrate-independent mechanism of adaptive search.

## Orientation

The genetic algorithm is the computational distillation of Darwin's mechanism. Holland developed it not primarily to model biological evolution but to extract the abstract mechanism of adaptation and apply it to hard optimization problems. The GA is the mathematical core of the adaptation thread — the machine you get when you abstract away all the biology and keep only selection, variation, and inheritance.

## Core

### The Algorithm

1. **Initialize** a population of N candidate solutions (strings, trees, programs — any representable structure)
2. **Evaluate** each candidate's fitness on the problem
3. **Select** candidates to reproduce, with probability proportional to fitness
4. **Recombine** pairs of selected candidates: pick a crossover point, swap substrings
5. **Mutate** offspring: flip bits with small probability
6. **Replace** old population with new generation
7. **Repeat** until convergence or termination criterion

The key operators: **selection** provides pressure toward higher fitness; **crossover** combines partial solutions from two parents; **mutation** maintains diversity and allows exploration of new regions.

### The Schema Theorem

Holland's schema theorem is the theoretical core. A **schema** is a template over the solution space — a string with some positions fixed and others free (wildcards). A schema matches any solution consistent with its fixed positions. The schema theorem states:

> Schemata with above-average fitness, short defining length, and low order receive exponentially increasing trials in subsequent generations.

The implications: the GA implicitly processes O(N³) schemata simultaneously while explicitly evaluating only N solutions. This is **implicit parallelism** — the GA is doing much more work than it appears to be, allocating increasing samples to the most promising partial solutions.

**Defining length** is the distance between a schema's outermost fixed positions; short defining length means crossover is unlikely to disrupt the schema. **Order** is the number of fixed positions; low-order schemata are the building blocks.

### The Building Blocks Hypothesis

Following from the schema theorem: the GA works by identifying short, low-order, high-fitness schemata (building blocks) and recombining them into progressively longer, higher-order, higher-fitness schemata. Adaptation is an incremental assembly of successful partial solutions.

This is empirically supported for problems with low epistasis (where partial solutions combine approximately independently) and breaks down for highly epistatic problems (where interactions between parts make partial solutions non-additive). The NK model makes this precise: at high K, building blocks lose their independence and the GA struggles. See `concepts/complexity/fitness-landscapes.md`.

### Extensions and Variants

**Genetic programming** (Koza) applies the GA to programs rather than fixed-length strings: a population of computer programs evolves toward a target behavior. This extends the paradigm to the open-ended domain of program search.

**Evolutionary strategies** (Rechenberg, Schwefel) apply evolutionary computation to continuous parameter spaces with self-adapting mutation rates — often more efficient than GAs for continuous optimization.

**Differential evolution**, **particle swarm optimization**, and **CMA-ES** are related gradient-free optimization methods that share the population-based, variation-and-selection structure without the biological metaphor.

**Neuroevolution** applies evolutionary algorithms specifically to neural networks — evolving weights, architectures, or both. See `concepts/computation/neuroevolution.md`.

## Connections

**Adaptation** (`concepts/complexity/adaptation.md`) — GAs are the computational formalization of the adaptation mechanism; the schema theorem is the mathematical explanation of why selection-and-variation works.

**Fitness landscapes** (`concepts/complexity/fitness-landscapes.md`) — GAs search fitness landscapes; the NK model analyzes when they succeed and when they fail.

**Neuroevolution** (`concepts/computation/neuroevolution.md`) — GAs applied to neural network architecture and weight search; bridges evolutionary computation and deep learning.

**Complex adaptive systems** (`concepts/complexity/complex-adaptive-systems.md`) — Holland's CAS framework uses the GA as the core adaptation mechanism for agents with internal schemas.

**Adaptation thread** (`synthesis/adaptation-thread.md`) — the full context for where GAs sit in the history of adaptation as a concept.

## Sources

- `sources/books/holland-hidden-order-1995.md` — Holland's account; the classifier system and its connection to GAs

## Open Questions

- When does the building blocks hypothesis hold, and is there a sharp characterization of the problem classes where GAs outperform gradient-based methods?
- Is there a principled theory for when evolutionary search should be preferred over gradient descent for neural network optimization?
- Can the schema theorem be extended to continuous and non-string representations in a way that preserves its theoretical force?
