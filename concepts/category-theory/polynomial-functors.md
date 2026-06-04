---
type: concept
name: "Polynomial Functors"
domain: category-theory
related_domains: [computation, dynamics, complexity]
status: stub
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Polynomial Functors

> The category **Poly** of polynomial functors on Set — proposed by Spivak and Niu as a mathematical theory of *interaction*. Each polynomial functor encodes an interface in which the set of available "actions" can depend on the current "position"; morphisms compose these interfaces. Poly is rich enough to host open interactive dynamical systems with mode-dependent interfaces and to underwrite a broad class of compositional agent and learner constructions.

## Orientation

Polynomial functors generalize the data of "for each position, a set of directions" — equivalently, a dependent type `(s : S) → A(s)`. Their morphisms compose like lenses do, and the resulting category Poly is monoidal in several useful ways, with internal-hom and other structure. Spivak & Niu's 2021 book *Polynomial Functors* develops Poly as a setting for **interactive dynamical systems**: systems whose available interactions at a given moment depend on their current state. This is what distinguishes Poly from the input/output picture of plain wiring diagrams, where the interface is fixed and state-independent.

## Core

(stub — to be filled when this node develops)

## Connections

- Generalizes [[wiring-diagrams]] in the direction needed for systems with state-dependent interfaces — agents that can perform different actions depending on context.
- The substrate of the **interactive** side of AlgebraicDynamics.jl, complementing the input/output side built on wiring diagrams.
- Closely related to [[lenses-and-optics]]: Poly morphisms are a generalization of lenses and the optic constructions of [[categorical-cybernetics]].
- A natural target for compositional models of [[reinforcement-learning|RL]] agents and active-inference agents (cf. [[sources/papers/smithe-bayesian-brain-2023]]).

## Sources

- [[sources/books/spivak-niu-polynomial-functors-2021]] — *Polynomial Functors: A Mathematical Theory of Interaction*.
