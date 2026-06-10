---
type: source-paper
title: "Categorical Foundations of Gradient-Based Learning"
author: [geoffrey-cruttwell, bruno-gavranovic, neil-ghani, paul-wilson, fabio-zanasi]
year: 2022
status: queued
domain: category-theory
related_domains: [computation, complexity]
key_concepts: [lenses-and-optics, categorical-cybernetics, parametric-lens, backprop]
published_in: esop
---

# Categorical Foundations of Gradient-Based Learning — Cruttwell, Gavranović, Ghani, Wilson & Zanasi (2022)

> arXiv:2103.01931 (ESOP 2022). Recasts supervised deep learning as composition in a category of **parametric lenses**: a learner is a morphism whose forward pass predicts and whose backward pass propagates the gradient, with the optimiser, loss, and learning rate each a modular categorical component.

## Key Contribution

Where *Backprop as Functor* (Fong–Spivak–Tuyéras 2019) showed learning is functorial, this paper gives the full compositional anatomy: a neural network, its loss function, its optimiser, and its update rule are each separate components in `Para(Lens)` / `Para(Optic)`, and backpropagation is exactly the composition of their backward passes. Changing optimiser or loss becomes swapping a component, not rewriting the chain rule. This is the paper that makes "a learner is a parametric optic" precise and implementable, and it is the missing middle of the vault's learning-agent chain — it sits directly between [[sources/papers/fong-spivak-tuyeras-backprop-functor-2019|Backprop as Functor]] and [[sources/papers/hedges-rl-categorical-cybernetics-2024|RL in Categorical Cybernetics]].

## Vault Relevance

Core source for [[concepts/category-theory/categorical-cybernetics]]; the gradient-learning instance of the `Para(Optic)` story built on [[concepts/category-theory/lenses-and-optics]]. Shares authorship and machinery with [[sources/papers/capucci-categorical-cybernetics-2021]]. Connects to [[geoffrey-cruttwell]], [[bruno-gavranovic]], [[neil-ghani]]. For a compositional modeling lab, this is the template for an agent whose backward pass is a gradient — the learning-agent counterpart to the best-response (games) and Bayesian-inversion (active inference) backward passes.
