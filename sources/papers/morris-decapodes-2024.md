---
type: source-paper
title: "Decapodes: A Diagrammatic Tool for Representing, Composing, and Computing Spatialized PDEs"
author: [evan-patterson, james-fairbanks]
year: 2024
status: queued
domain: category-theory
related_domains: [dynamics, computation, complexity]
key_concepts: [compositional-modeling, multiphysics, discrete-exterior-calculus, open-systems, simulation, algebraicjulia]
---

# Decapodes — Morris, Baas, Arias, Gatlin, Patterson & Fairbanks (2024)

> *Journal of Computational Science* 81 (2024); arXiv:2401.17432. A diagrammatic tool (and Julia library, Decapodes.jl) for representing, composing, and computing spatialized partial differential equations — the synthesis of Applied Category Theory composition techniques with Discrete Exterior Calculus (DEC) for differential operators.

## Key Contribution

Decapodes is the practical realization of compositional modeling for physics: PDE systems are specified in a human-readable declarative DSL, composed hierarchically along shared boundaries (open-systems style), and generalized over arbitrary manifolds while remaining performant. It is the working software substrate for the "compose clean dynamical subsystems, then simulate and observe" laboratory program — correct-by-construction assembly plus reproducible execution. The broader AlgebraicJulia stack also supports **agent-based modeling via graph rewriting**, where typed rewrite rules drive discrete-time simulations that are transparent, compositional, and serializable.

## Vault Relevance

Concrete tooling for [[concepts/category-theory/open-systems]] and the compositional-modeling counterpart to [[concepts/complexity/agent-based-modeling]]. Implements the [[sources/papers/vagner-spivak-lerman-open-dynamical-2015|open dynamical systems]] approach at scale. Connects to [[evan-patterson]] and [[james-fairbanks]] (AlgebraicJulia). The graph-rewriting ABM support is the practical home of typed-rewrite "birth of new agents" / open-ended structural change.
