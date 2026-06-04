---
type: concept
name: "Discrete Exterior Calculus"
domain: geometry
related_domains: [computation, dynamics, mechanics, category-theory]
status: stub
provenance: literature
extends: [differential-geometry]
instance_of: []
contrasts_with: []
---

# Discrete Exterior Calculus

> A rigorous discrete reformulation of the calculus of differential forms — defining discrete forms, the exterior derivative, the Hodge star, and the wedge product on simplicial complexes (or more generally on cell complexes) — designed to support numerical computation while preserving the structural identities of the continuous theory. Abbreviated **DEC**.

## Orientation

DEC was developed in the early 2000s by Anil Hirani in his Caltech PhD (advised by [[jerrold-marsden]]) and consolidated in the influential 2005 expository paper by Desbrun, Hirani, Leok, and Marsden. The motivation: standard finite-element and finite-difference discretizations of PDEs lose the underlying differential-geometric structure (Stokes' theorem, de Rham complex, exact-vs-closed distinction), which often matters for stability and conservation. DEC preserves that structure by working with cochains on a simplicial complex, defining the discrete exterior derivative as the coboundary operator (giving $d \circ d = 0$ exactly, not approximately), and mediating between primal and dual cells via a discrete Hodge star.

The framework has had two distinct uptake stories:
1. **Computational geometry and graphics** (Desbrun, Hirani, Leok and successors) — discrete differential geometry on meshes, with applications to surface processing, geometric flows, fluid simulation.
2. **Categorical compositional modelling** (AlgebraicJulia, Decapodes 2024) — DEC operators as the *differential* layer inside a *compositional* multiphysics PDE framework.

## Core

(stub — to be filled when this node develops)

## Connections

- Discrete companion to [[differential-geometry]]; the discrete forms and exterior derivative recover the continuous theory's identities up to mesh refinement.
- Substrate for the AlgebraicJulia [[concepts/category-theory/open-systems|open-systems]] / [[concepts/category-theory/wiring-diagrams|wiring-diagrams]] approach to multiphysics PDEs — see [[sources/papers/morris-decapodes-2024]] for the categorical reformulation in Decapodes.
- Connects to [[concepts/mechanics/INDEX|geometric mechanics]] via [[melvin-leok]]'s discrete-variational-integrators line, also rooted in Marsden's program.

## Sources

- [[sources/papers/hirani-discrete-exterior-calculus-2003]] — PhD thesis; the foundational technical reference.
- [[sources/papers/desbrun-hirani-leok-marsden-dec-2005]] — expository 2005 paper that disseminated the framework broadly.
- [[sources/papers/morris-decapodes-2024]] — categorical reformulation inside AlgebraicJulia (Decapodes.jl).
