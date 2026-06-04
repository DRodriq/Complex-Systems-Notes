---
type: concept
name: "Persistent Homology"
domain: dynamics
related_domains: [information, computation]
status: stub
provenance: literature
extends: []
instance_of: []
precedes: []
contrasts_with: []
tags: [TDA, topology, homology, persistence, point-cloud, Betti-numbers]
---

# Persistent Homology

> A method from topological data analysis (TDA) that detects multi-scale structure in point cloud data by tracking which topological features — connected components, loops, voids — are born and die as a resolution parameter is varied. Features that persist across a wide range of scales are considered significant; those that appear and vanish quickly are considered noise.

## Orientation

Persistent homology bypasses the need to choose a clustering resolution by examining all resolutions simultaneously and recording the full birth–death history of topological features. The output is a *persistence diagram* (or barcode), in which each feature is a point or bar spanning its lifespan. Long bars correspond to genuine structure; short bars correspond to noise. This makes persistent homology a scale-free, parameter-light alternative to density-based or distance-based clustering, and gives a formal language for talking about when a cluster is "real."

## Connections

**Attractors** (`concepts/dynamics/attractors.md`) — H0 persistent features (connected components) are basin-of-attraction analogs; H1 features (loops) correspond to limit cycles; H2 features (voids) identify topological holes in the trajectory.

**Lyapunov exponents** (`concepts/dynamics/lyapunov-exponents.md`) — both characterize dynamical structure across scales; persistent homology is geometrically richer but less directly tied to information production.

**Manifold hypothesis** (`concepts/dynamics/manifold-hypothesis.md`) — persistent homology is one of the primary tools for characterizing the topology of a data manifold.

## Sources

- Edelsbrunner, H. & Harer, J. *Computational Topology: An Introduction.* AMS, 2010. — The standard textbook; covers simplicial homology, filtrations, and persistent homology from first principles.
- Carlsson, G. "Topology and Data." *Bulletin of the American Mathematical Society*, 46(2), 255–308, 2009. — The key survey paper introducing TDA to a broad audience; accessible entry point.
