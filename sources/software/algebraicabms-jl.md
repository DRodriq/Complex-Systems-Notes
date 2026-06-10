---
type: source-software
name: "AlgebraicABMs.jl"
repo: "https://github.com/AlgebraicJulia/AlgebraicABMs.jl"
language: Julia
license: MIT
maintenance: research-grade
year: 2024
domain: category-theory
related_domains: [computation, complexity]
maintained_by: [kris-brown]
builds_on: [algebraicrewriting-jl, catlab-jl]
implements: [brown-categorical-rewriting-2023, agent-based-modeling]
key_concepts: [agent-based-modeling, graph-rewriting, applied-category-theory]
---

# AlgebraicABMs.jl

> **Stochastic graph rewriting for agent-based modeling**, in the AlgebraicJulia ecosystem. Agents and their world are an attributed C-set (acset); the model evolves by firing typed rewrite rules whose timing is drawn stochastically — making ABM a special case of categorical rewriting rather than a separate paradigm.

## What it is

AlgebraicABMs realizes the [[sources/papers/brown-categorical-rewriting-2023|computational category-theoretic rewriting]] engine as an agent-based-modelling framework. The state of the world is an acset; agent behaviours, births, deaths, and rewirings are double-pushout (and related) rewrite rules over it; and a stochastic scheduler (continuous-time / clock-based rule firing) drives the dynamics. Because every transition is a lawful rewrite on a typed structure, structural change stays correct-by-construction — the property that hand-rolled imperative ABM glue silently loses. The canonical demonstration in the repo is Conway's Game of Life expressed as rewrite rules (`docs/literate/game_of_life.jl`).

It sits on top of [[sources/papers/patterson-categorical-data-structures-2022|acsets]] (Catlab) and the AlgebraicRewriting layer; it is the ecosystem's answer to "ABM with structural change" and aims, eventually, at the role conventional frameworks like Agents.jl / NetLogo fill — but from a categorical substrate that gives composition and verification for free.

## Maintenance status (as of June 2026)

**Research-grade / pre-release.** MIT-licensed, not archived, but **last code activity ~August 2025** (last commit to `main` ~June 2025) — roughly a year quiet as of this writing. **No tagged releases**, and the README explicitly warns the API/behaviour is not yet stable ("contact us before assuming API stability"). 11 stars, ~25 open issues. So it is a usable research artifact and the reference implementation of the idea, but not production tooling, and development cadence has slowed — the "dormant / research-grade" read is accurate; treat the README's "active development" as aspirational.

## Vault Relevance

The executable instance of the structural-dynamics idea in [[concepts/category-theory/applied-category-theory]] and the ACT-native counterpart to [[concepts/complexity/agent-based-modeling]]. Implements [[sources/papers/brown-categorical-rewriting-2023]]; maintained within the AlgebraicJulia group ([[kris-brown]], [[institutions/topos-institute]] orbit). For a compositional simulation lab, this is the closest existing tool to a graph-rewriting structural-dynamics layer — worth tracking for reuse rather than reinventing, with the caveat that its pre-release status means depending on it is a research bet, not a stable foundation.
