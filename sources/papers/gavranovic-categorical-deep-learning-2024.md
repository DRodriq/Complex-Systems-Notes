---
type: source-paper
title: "Categorical Deep Learning: An Algebraic Theory of All Architectures"
author: [bruno-gavranovic, paul-lessard, andrew-dudzik, tamara-von-glehn, joao-araujo, petar-velickovic]
year: 2024
status: queued
domain: category-theory
related_domains: [computation, complexity]
key_concepts: [categorical-cybernetics, applied-category-theory, equivariance, monad-algebra]
published_in: icml
---

# Categorical Deep Learning: An Algebraic Theory of All Architectures — Gavranović, Lessard, Dudzik, von Glehn, Araújo & Veličković (2024)

> arXiv:2402.15332 (ICML 2024, position paper). Argues that the right language for neural-network architecture is category theory: layers and their constraints (equivariance, recurrence, structure preservation) are uniformly expressed as **(co)algebras of (co)monads** and parametric maps, generalising the geometric-deep-learning programme from groups to arbitrary categorical structure.

## Key Contribution

Geometric deep learning unified architectures via group-equivariance; this paper argues that program is a special case of a categorical one — replace "group action" with "monad/comonad algebra" and the same template covers sequence models, GNNs, and structure-respecting maps that groups cannot express. The significance for the vault is sociological as much as technical: it is the most direct bridge from the applied-category-theory programme into mainstream machine learning, authored partly from inside Google DeepMind. It marks the point where the `Para(Optic)` / categorical-learning line stops being a niche reformulation and starts making architecture-design claims the ML field can test.

## Vault Relevance

Extends [[concepts/category-theory/categorical-cybernetics]] and [[concepts/category-theory/applied-category-theory]] toward mainstream ML. Sibling to [[sources/papers/cruttwell-gradient-based-learning-2022]] (shared author [[bruno-gavranovic]]). Connects to [[paul-lessard]], [[petar-velickovic]]. Evidence for the cluster's "does this matter outside CT?" question — the answer the vault should track as the categorical-ML thread develops.
