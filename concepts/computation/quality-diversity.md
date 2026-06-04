---
type: concept
domain: computation
related_domains: [complexity]
provenance: mixed
status: developing
relates_to:
  - target: neuroevolution
    relation: extends
  - target: genetic-algorithms
    relation: extends
  - target: concepts/complexity/fitness-landscapes
    relation: overlaps
tags: [quality-diversity, MAP-Elites, illumination, behavioral-diversity, Cully]
---

# Quality Diversity

> A class of evolutionary algorithms that optimize for both performance quality and behavioral diversity simultaneously — maintaining an archive of high-performing solutions across a space of behavioral descriptors rather than converging to a single optimum.

## Orientation

Standard optimization — including GAs and RL — seeks a single best solution. Quality-diversity (QD) algorithms instead seek to fill a behavior space with the best possible solution for each behavioral niche. The output is not one answer but a map of the best-known solutions across the full range of behavioral variation.

This shift is motivated by several insights: many real problems have multiple valid solutions; a diverse repertoire is more robust to changing conditions than a single optimized solution; and diversity in evolutionary search prevents premature convergence and enables the discovery of unexpected high-quality solutions.

## Core

### MAP-Elites

The foundational QD algorithm. The behavior space is discretized into a grid of cells, each defined by a behavioral descriptor (e.g., limb usage pattern for a robot, move distribution for a game player). During evolution, when a new solution is evaluated, it is placed in the cell corresponding to its behavioral descriptor. If the cell is empty or the new solution outperforms the current occupant, it replaces it. The result is an **illumination** of the behavior space — the best-known solution for each behavioral niche.

The algorithm is remarkably simple and has proven effective across robotics (damage recovery), game playing, and search problems. Its power comes from maintaining diversity explicitly rather than as a side effect: the archive structure forces exploration of behavioral space regardless of performance.

### Behavioral Descriptors

The choice of behavioral descriptors is the key design decision. Descriptors should capture the behavioral variation that matters for the application — which dimensions of behavior are we interested in preserving? In locomotion: gait symmetry and body contact pattern. In game playing: piece-type usage, positional preference. In molecular design: chemical properties.

Recent work (AURORA, latent space illumination) learns the behavioral descriptors automatically rather than specifying them by hand — using unsupervised learning to discover the dimensions of behavioral variation in the data.

### Relationship to Adaptation and CAS

QD can be read as a model of adaptive radiation: the process by which a single ancestral lineage diversifies into multiple ecological niches. Rather than all evolution converging on a single peak, QD maintains a diverse population of specialists. This is closer to how biological evolution actually works in diverse environments than single-objective optimization.

The archive structure is also a model of niche construction: the cells that are filled define the landscape of what is known to be achievable, and evolution fills the gaps by discovering solutions near existing archive entries.

## Connections

**Neuroevolution** (`concepts/computation/neuroevolution.md`) — QD can evolve neural network policies using MAP-Elites, maintaining a diverse archive of controllers for different behavioral niches.

**Genetic algorithms** (`concepts/computation/genetic-algorithms.md`) — QD extends GAs with an explicit diversity mechanism; the archive replaces the single fitness ranking with a multi-niche structure.

**Fitness landscapes** (`concepts/complexity/fitness-landscapes.md`) — QD can be understood as searching for all local optima simultaneously rather than a single global one.

**Adaptation thread** (`synthesis/adaptation-thread.md`) — QD is the adaptation mechanism in a multi-niche form; closer to biological adaptive radiation than to single-objective optimization.

## Sources

- `sources/papers/cully-quality-diversity-2017.md`
- `sources/papers/cully-qd-stochastic-2021.md`
- `sources/papers/lim-dynamics-aware-qd-2022.md`

## Open Questions

- What is the right behavioral descriptor for general-purpose agents, and can it be learned in an unsupervised way that captures behaviorally meaningful variation?
- Does QD produce more robust solutions than single-objective optimization in deployment settings with distribution shift?
- Is there a complexity science interpretation of QD archives — do they represent something like a fitness landscape's full basin structure?
