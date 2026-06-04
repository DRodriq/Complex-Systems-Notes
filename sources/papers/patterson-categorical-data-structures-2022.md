---
type: source-paper
title: "Categorical Data Structures for Technical Computing"
author: [evan-patterson, owen-lynch, james-fairbanks]
year: 2022
status: queued
domain: category-theory
related_domains: [computation]
key_concepts: [acsets, catlab, categorical-data-structures, algebraic-julia]
---

# Categorical Data Structures for Technical Computing — Patterson, Lynch & Fairbanks (2022)

> Compositionality (arXiv:2106.04703). Introduces **ACSets** (attributed C-Sets) as a general data structure for technical computing, implemented in **Catlab.jl** — the data-structure substrate of the AlgebraicJulia ecosystem.

## Key Contribution

ACSets generalize relational databases, graphs, simplicial complexes, Petri nets, and many other combinatorial structures into a single framework parameterized by a small category $\mathbf{C}$ (the "schema"). They are simultaneously a categorical construction and a practical data structure, supporting efficient queries, structured-cospan composition, and morphism-based transformations. The paper grounds the data-structure side of the AlgebraicJulia stack.

## Vault Relevance

Foundational source for the implementation side of [[concepts/category-theory/wiring-diagrams]] and [[concepts/category-theory/open-systems]]. Connects to [[evan-patterson]] and [[james-fairbanks]].
