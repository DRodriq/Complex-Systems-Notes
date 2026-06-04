---
type: concept
domain: complexity
related_domains: [computation, applied]
provenance: mixed
status: developing
relates_to:
  - target: adaptation
    relation: foundation-for
  - target: complex-adaptive-systems
    relation: foundation-for
  - target: concepts/computation/genetic-algorithms
    relation: foundation-for
  - target: edge-of-chaos
    relation: overlaps
tags: [fitness-landscapes, NK-model, Kauffman, ruggedness, evolvability]
---

# Fitness Landscapes

> Kauffman's geometric model of adaptive search: a high-dimensional space where each point represents a possible configuration and elevation represents fitness, with the structure (smoothness or ruggedness) of the surface determining how effectively selection and variation can navigate it.

## Orientation

The fitness landscape metaphor was introduced by Sewall Wright in 1932 and formalized by Stuart Kauffman through the NK model. It provides a way to think geometrically about the problem of adaptation: what is the shape of the space being searched, and how does that shape determine the speed and effectiveness of the search?

## Core

### The Landscape Metaphor

Every possible genotype (or configuration of a system's variables) maps to a fitness value. Plotting this creates a surface — peaks are high-fitness configurations, valleys are low-fitness ones. Adaptive evolution is movement on this surface: populations move uphill toward higher fitness via selection, with mutation and recombination providing the steps.

The landscape metaphor immediately raises questions about landscape structure. A smooth, single-peaked landscape (Mt. Fuji) allows simple hill-climbing to find the global optimum. A rugged landscape with many peaks of varying height (Badlands) causes hill-climbing to get stuck on local optima. The structure of the landscape determines the effectiveness of any search strategy.

### Kauffman's NK Model

Kauffman's NK model makes the landscape concept quantitative. A system has N binary variables (genes), each contributing to fitness through interactions with K others chosen at random. When K=0, each gene contributes independently — the landscape is smooth and a single global optimum is accessible. When K=N-1, every gene interacts with every other — the landscape is maximally rugged, effectively random, with exponentially many local optima.

At intermediate K, the landscape has a structured ruggedness. The key finding: adaptive search (analogous to hill-climbing) is most effective at intermediate K, near the phase transition between ordered (K=0) and chaotic (K=N-1) landscape regimes. This is the NK model's contribution to the edge-of-chaos hypothesis: the most evolvable systems are near a phase transition in their fitness landscape structure.

### Epistasis

**Epistasis** is the interaction between genes (or variables) in determining fitness — the degree to which a change at one locus depends on the values at others. High epistasis means K is high, the landscape is rugged, and building blocks (partially good solutions) do not combine additively. Low epistasis means K is low, the landscape is smooth, and evolution or GAs can effectively combine partial solutions.

Epistasis is the structural concept that determines when Holland's building blocks hypothesis holds and when it fails.

### Implications for Evolvability

The fitness landscape framing makes evolvability a structural property of the system being evolved, not just a property of the evolutionary process. Systems with low K are highly evolvable — selection can navigate the smooth landscape efficiently. Systems with high K are barely evolvable — the landscape is too rugged for local search to make progress.

This means that the architecture of a system (how its parts interact) determines whether it can be effectively improved by an adaptive process. Modular architectures, where components can be varied somewhat independently, have lower effective K and higher evolvability. This is a candidate explanation for why biological organisms evolved modular organization.

The same logic applies to neural architecture search: some network architectures are more amenable to gradient-based optimization (lower effective K in the weight space) than others.

## Connections

**Adaptation** (`concepts/complexity/adaptation.md`) — fitness landscapes are the geometric object that adaptation navigates; the landscape structure determines the effectiveness of any adaptive process.

**Genetic algorithms** (`concepts/computation/genetic-algorithms.md`) — GAs search fitness landscapes; the schema theorem and building blocks hypothesis describe how they do so; NK-model analysis reveals when they succeed.

**Edge of chaos** (`concepts/complexity/edge-of-chaos.md`) — the NK model shows that the most evolvable landscapes are near the ordered-chaotic phase transition; this is one of the primary lines of evidence for the edge-of-chaos hypothesis.

**Adaptation thread** (`synthesis/adaptation-thread.md`) — the full context for this concept.

## Sources

- `sources/books/kauffman-at-home-in-the-universe-1995.md`
- `sources/books/kauffman-origins-of-order-1993.md`

## Open Questions

- Do the fitness landscapes of real biological systems have NK-model-like structure, or is the NK model too abstract to make contact with molecular biology?
- Is there an analog of the fitness landscape for neural network weight space — and does the NK model's phase transition analysis apply?
- Can evolvability itself be selected for, and what are the constraints on this process?
