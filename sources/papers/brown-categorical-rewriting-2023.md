---
type: source-paper
title: "Computational Category-Theoretic Rewriting"
author: [kris-brown, evan-patterson, tyler-hanks, james-fairbanks]
year: 2023
status: queued
domain: category-theory
related_domains: [computation, complexity]
key_concepts: [applied-category-theory, open-systems, graph-rewriting, acsets]
published_in: jlamp
---

# Computational Category-Theoretic Rewriting — Brown, Patterson, Hanks & Fairbanks (2023)

> Journal of Logical and Algebraic Methods in Programming 134 (2023); earlier ICGT 2022 (LNCS). Implements **double-pushout (DPO), single-pushout (SPO), and sesqui-pushout (SqPO) rewriting for attributed C-sets (acsets)** in AlgebraicJulia — i.e. lawful, type-respecting structural rewriting of categorical data structures, in running code.

## Key Contribution

This is the engine that makes "structural change as a categorical operation" executable. Rewriting an acset by a DPO rule changes the *structure* of a model (adds/removes objects and morphisms) while staying correct-by-construction with respect to its schema. That is exactly the mechanism a compositional simulation needs for birth/death of subsystems, rewiring, and settlement formation — structural dynamics that imperative glue would express but silently strip of their guarantees. The vault tracked the acset data structure ([[sources/papers/patterson-categorical-data-structures-2022]]) but not the rewriting calculus built on it; this paper is the missing operational layer, and the formal core under AlgebraicJulia's agent-based-modelling-via-rewriting capability.

## Vault Relevance

Operational source for [[concepts/category-theory/applied-category-theory]] and the AlgebraicJulia stack; the rewriting counterpart to [[sources/papers/patterson-categorical-data-structures-2022|acsets]]. Directly relevant to [[concepts/complexity/agent-based-modeling]] (ABM via graph rewriting) and to the structural-dynamics layer of any compositional modeling lab. **Implemented in** [[sources/software/algebraicabms-jl]], which builds the ABM framework on this engine. Connects to [[kris-brown]], [[evan-patterson]], [[tyler-hanks]], [[james-fairbanks]].
