---
type: concept
domain: information
related_domains: [computation]
provenance: mixed
status: stub
relates_to:
  - target: kolmogorov-complexity
    relation: extends
  - target: effective-complexity
    relation: overlaps
tags: [logical-depth, Bennett, computational-effort, organized-complexity]
---

# Logical Depth

> Bennett's complexity measure: the computational effort required to produce an object from its most concise description — capturing organized complexity as the residue of a long causal process rather than as incompressibility.

## Orientation

Logical depth addresses the core failure of Kolmogorov complexity as a complexity measure: a random string has maximum K(x) but minimal organized complexity. Bennett's insight is that organized complexity is not about description length but about the length of the *computation* from description to object. Complex objects are those that could not have arisen quickly — they bear evidence of a long computational history.

## Core

An object has high logical depth if: (1) its shortest description (Kolmogorov complexity) is short relative to the object's length — meaning it has genuine regularities — and (2) the time to compute the object from that description is long.

A random string has short description (random seed) but trivial computation: expand the seed via pseudo-random function. Shallow. A crystal has short description (lattice parameter) and trivial computation: tile. Shallow. A living organism has short description (genome) but enormously long computation: development, protein folding, cell differentiation, growth. Deep.

The measure captures the intuition that living things, economies, and evolved artifacts carry evidence of a long causal process — that their structure is the result of computation that could not be bypassed. You cannot get a brain quickly; the depth is real.

Like Kolmogorov complexity, logical depth is not computable. But it provides the theoretical concept for which empirical proxies can be constructed.

## Connections

**Kolmogorov complexity** (`concepts/information/kolmogorov-complexity.md`) — the description length measure that logical depth builds on; depth requires first finding the shortest description.

**Effective complexity** (`concepts/information/effective-complexity.md`) — complementary: effective complexity measures what the schema says; logical depth measures how long it takes to execute the schema.

**Measuring complexity thread** (`synthesis/measuring-complexity-thread.md`) — full context.

## Open Questions

- Is logical depth the right measure for biological complexity, or does it conflate the complexity of the organism with the complexity of evolution?
- What is the logical depth of a trained neural network — is it the depth of the training process, or the depth of inference?
