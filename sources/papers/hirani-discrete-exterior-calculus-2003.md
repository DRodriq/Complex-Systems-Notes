---
type: source-paper
title: "Discrete Exterior Calculus"
author: [anil-hirani]
year: 2003
status: queued
domain: geometry
related_domains: [computation, dynamics, mechanics]
key_concepts: [discrete-exterior-calculus, dec, differential-forms, simplicial-complexes, geometric-numerics]
---

# Discrete Exterior Calculus — Hirani (2003)

> PhD thesis, Caltech (advised by [[jerrold-marsden]]). Establishes **Discrete Exterior Calculus (DEC)** as a rigorous discrete reformulation of the calculus of differential forms — defining discrete forms, the discrete exterior derivative $d$, the Hodge star, discrete vector fields, and the relations among them — on simplicial complexes with sufficient structure to support numerical computation.

## Key Contribution

Provides the foundational discrete analogues of: differential forms (as cochains on a simplicial complex), exterior derivative (the coboundary operator, with sign conventions chosen to make $d \circ d = 0$ hold), Hodge star (mediating between primal and dual cells of an oriented simplicial complex), wedge product, and the resulting discrete versions of Stokes' theorem and the de Rham complex. The thesis was the first systematic, computational presentation of these ideas in a form usable for numerical PDE work.

## Vault Relevance

Anchor source for [[concepts/geometry/discrete-exterior-calculus]]; the technical foundation later used (and recast categorically) in the Decapodes line of AlgebraicJulia work — see [[sources/papers/morris-decapodes-2024]]. Connects to [[anil-hirani]] and [[jerrold-marsden]].
