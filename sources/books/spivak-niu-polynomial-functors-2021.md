---
type: source-book
title: "Polynomial Functors: A Mathematical Theory of Interaction"
author: [david-spivak, nelson-niu]
year: 2021
status: queued
domain: category-theory
related_domains: [computation, dynamics]
key_concepts: [polynomial-functors, poly, interaction, open-interactive-systems, dependent-types]
---

# Polynomial Functors — Spivak & Niu (2021 draft; Cambridge UP 2025)

> Book-length treatment of the category **Poly** of polynomial functors on Set, framed as a mathematical theory of *interaction*. Polynomial functors generalize the data of "for each position, a set of available actions," giving a categorical setting for open systems whose interfaces depend on their state.
>
> **Publication status:** circulated as a draft from 2021; formally published by **Cambridge University Press, online 27 September 2025** (ISBN 9781009576710). The slug retains `-2021` for link stability — cite the Cambridge 2025 edition as canonical.

## Orientation

The book builds Poly's monoidal and exponential structure from the ground up, then uses it to host open *interactive* dynamical systems — systems where the actions available at a moment depend on the system's current mode. This complements the input/output picture of plain wiring diagrams, which assume fixed interfaces.

## Key Ideas

- Polynomial functors on Set; Poly as a category
- Composition: each `(s : S) → A(s)` interface composes by substitution
- Lens-like and prism-like morphisms; relation to optic categories
- Interactive dynamical systems with mode-dependent interfaces
- Foundation of the "interactive" side of AlgebraicDynamics.jl

## Vault Relevance

Anchor source for [[concepts/category-theory/polynomial-functors]]. Connects to [[concepts/category-theory/lenses-and-optics]] (Poly morphisms generalize lenses) and to the interactive-agent line in [[concepts/category-theory/categorical-cybernetics]].
