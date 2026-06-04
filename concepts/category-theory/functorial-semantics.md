---
type: concept
name: "Functorial Semantics"
domain: category-theory
related_domains: [computation, philosophy]
status: stub
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Functorial Semantics

> Lawvere's framing: a *theory* is a category, and a *model* of that theory is a structure-preserving functor into a target category. Syntax lives on one side; semantics on the other; the functor is the interpretation. Originates in Lawvere's 1963 thesis and underlies most of the structure/behaviour split in applied category theory.

## Orientation

Functorial semantics is the conceptual stance under most of contemporary applied category theory: define a category whose objects and morphisms encode the *syntax* of your domain (e.g. operations of an algebraic theory, wires of a wiring diagram, transitions of a Petri net), define a target category whose objects and morphisms encode the intended *semantics* (sets and functions, vector spaces, dynamical systems, probability kernels), and study functors between them. The functor is the interpretation; functoriality is the lawfulness of that interpretation under composition.

## Core

(stub — to be filled when this node develops)

## Connections

- The structural backbone of [[applied-category-theory]].
- Drives the distinction in [[open-systems]] between the syntactic operad (e.g. [[wiring-diagrams]]) and the semantic algebra (e.g. open dynamical systems).
- The Baez–Pollard result that the *rate equation* assignment for open reaction networks is functorial (see [[sources/papers/baez-pollard-reaction-networks-2017]]) is functorial semantics applied to reaction networks.
- The Baez–Fong–Pollard "black-boxing" functor for Markov processes is the steady-state input/output semantics of stochastic open systems.

## Sources

- [[sources/papers/lawvere-functorial-semantics-1963]] — the original thesis.
- [[sources/papers/baez-pollard-reaction-networks-2017]] — rate equation as a functor on open reaction networks.
- [[sources/papers/baez-fong-pollard-markov-2016]] — black-boxing as a functor for Markov processes.
