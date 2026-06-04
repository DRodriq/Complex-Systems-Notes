---
type: concept
name: "Lenses and Optics"
domain: category-theory
related_domains: [computation, complexity]
status: stub
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Lenses and Optics

> Bidirectional `(get, put)` processes — given a "small" view of a "big" state, *get* extracts the view and *put* writes an updated view back. Originating in database/programming-language theory, lenses were generalized in applied category theory to **optics**, a broad family of bidirectional composable processes that include lenses, prisms, traversals, and more. The substrate for "perceive state and act back on it," and the central building block of categorical cybernetics and open games.

## Orientation

Lenses (`get : S → A`, `put : S × A → S`) compose: a lens from `S` to `A` and a lens from `A` to `B` give a lens from `S` to `B`. This composition law makes lenses a category, and a number of variants (monomorphic, polymorphic, mixed-variance) and generalizations (prisms, traversals, grates) form related categories. Riley's 2018 paper *Categories of Optics* unified many of these under the **optic** construction. The categorical view of lenses-as-perception/action is what makes them the natural primitive for compositional agents.

## Core

(stub — to be filled when this node develops)

## Connections

- Underwrites [[compositional-game-theory]] (open games are built from lenses) and [[categorical-cybernetics]] (the `Para(Optic)` construction generalizes both games and learners).
- The "perceive and act" framing connects optics to active-inference / Bayesian-brain formalisms (cf. [[sources/papers/smithe-bayesian-brain-2023]]).
- [[polynomial-functors]] generalize lenses to mode-dependent interfaces — Poly morphisms are a strict generalization of lenses.
- Backpropagation has a clean lens/optic interpretation: gradient descent is a functor whose morphisms are lens-like (cf. [[sources/papers/fong-spivak-tuyeras-backprop-functor-2019]]).
- Reinforcement learning fits the same mould: Bellman backup is **value iteration as optic composition** — the value update is precomposition with an optic (cf. [[sources/papers/hedges-rl-categorical-cybernetics-2024]]).

## Sources

- [[sources/papers/riley-categories-optics-2018]] — *Categories of Optics*; unification of lens variants.
- [[sources/papers/fong-spivak-tuyeras-backprop-functor-2019]] — *Backprop as Functor*; learning as compositional.
- [[sources/papers/capucci-categorical-cybernetics-2021]] — `Para(Optic)` unifying games, learners, agents.
- [[sources/papers/hedges-rl-categorical-cybernetics-2024]] — RL in categorical cybernetics; value iteration as optic composition.
