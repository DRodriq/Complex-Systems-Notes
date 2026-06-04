---
type: source-paper
title: "Decapodes: A Diagrammatic Tool for Representing, Composing, and Computing Spatialized PDEs"
author: [luke-morris, andrew-baas, jesus-arias, maia-gatlin, evan-patterson, james-fairbanks]
year: 2024
status: queued
domain: category-theory
related_domains: [dynamics, computation, geometry, complexity]
key_concepts: [compositional-modeling, multiphysics, discrete-exterior-calculus, open-systems, simulation, algebraic-julia, decapodes]
---

# Decapodes — Morris, Baas, Arias, Gatlin, Patterson & Fairbanks (2024)

> *Journal of Computational Science* (2024); arXiv:2401.17432. A diagrammatic tool (and Julia library, **Decapodes.jl**) for representing, composing, and computing spatialized partial differential equations — synthesizing Applied Category Theory composition techniques with [[concepts/geometry/discrete-exterior-calculus|Discrete Exterior Calculus]] for the differential operators.

## Key Contribution

Decapodes is the practical realization of compositional modelling for physics. PDE systems are specified in a human-readable declarative DSL, composed hierarchically along shared boundaries in the open-systems style, and generalized over arbitrary manifolds while remaining performant. The categorical wiring-diagram apparatus from the [[james-fairbanks|Fairbanks]] / [[evan-patterson|Patterson]] AlgebraicJulia line ([[sources/papers/libkind-baas-patterson-fairbanks-operadic-dynamical-2021|Libkind et al. 2021]], [[sources/papers/libkind-structured-epidemic-2022|Libkind et al. 2022]]) provides the *composition substrate*; DEC ([[sources/papers/hirani-discrete-exterior-calculus-2003|Hirani 2003]], [[sources/papers/desbrun-hirani-leok-marsden-dec-2005|Desbrun et al. 2005]]) provides the *differential operators*; the contribution is the synthesis and its working software realization.

The broader AlgebraicJulia stack also supports **agent-based modelling via graph rewriting**, where typed rewrite rules drive discrete-time simulations that are transparent, compositional, and serializable — extending the compositional-modelling stance from continuous to discrete dynamics.

## Author Affiliations

[[luke-morris|Morris]] and [[andrew-baas|Baas]] work in [[james-fairbanks|Fairbanks]]'s orbit. [[jesus-arias|Arias]] and [[maia-gatlin|Gatlin]] are at [[institutions/gtri|GTRI]] (Georgia Tech Research Institute). [[evan-patterson|Patterson]] is at the [[institutions/topos-institute|Topos Institute]]. [[james-fairbanks|Fairbanks]] is at the University of Florida.

## Vault Relevance

Concrete tooling for [[concepts/category-theory/open-systems]] and the compositional-modelling counterpart to [[concepts/complexity/agent-based-modeling]]. Implements the [[sources/papers/vagner-spivak-lerman-open-dynamical-2015|open dynamical systems]] approach at scale, with DEC as the discrete-differential-operator layer. Anchor of the categorical-multiphysics line in the vault's CT cluster.
