---
type: source-paper
title: "Backprop as Functor: A Compositional Perspective on Supervised Learning"
author: [brendan-fong, david-spivak, remy-tuyeras]
year: 2019
status: queued
domain: category-theory
related_domains: [computation]
key_concepts: [backpropagation, learning, functorial-semantics, gradient-descent]
---

# Backprop as Functor — Fong, Spivak & Tuyéras (2019)

> LICS 2019 (arXiv:1711.10455). Shows that **backpropagation can be defined as a functor** from a category of "parameterized maps" to a category of "learners," making gradient-descent training a compositional structure rather than an architectural accident.

## Key Contribution

Defines a category $\mathbf{Learn}$ whose morphisms encode (forward map, backward gradient, update rule) and shows that the standard gradient-descent training procedure lifts to a functor from parameterized smooth maps into $\mathbf{Learn}$. Composition of parameterized maps becomes composition of learners — i.e., training a composite network is the composite of training its parts. This is the technical anchor for treating learning as a compositional phenomenon, and it directly prefigures the `Para(Optic)` construction of categorical cybernetics.

## Vault Relevance

Cited in [[concepts/category-theory/lenses-and-optics]] and [[concepts/category-theory/categorical-cybernetics]]; a key example of [[concepts/category-theory/functorial-semantics]] applied to ML. Connects to [[brendan-fong]], [[david-spivak]], [[remy-tuyeras]].
