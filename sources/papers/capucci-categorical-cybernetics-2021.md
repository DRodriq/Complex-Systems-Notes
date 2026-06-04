---
type: source-paper
title: "Towards Foundations of Categorical Cybernetics"
author: [matteo-capucci, bruno-gavranovic, jules-hedges, eigil-rischel]
year: 2021
status: queued
domain: category-theory
related_domains: [computation, complexity, philosophy]
key_concepts: [categorical-cybernetics, para-optic, open-games, learners, agents]
---

# Towards Foundations of Categorical Cybernetics — Capucci, Gavranović, Hedges & Rischel (2021)

> ACT 2021 (arXiv:2105.06332). Introduces the **`Para(Optic)`** construction — parameterized morphisms over an optic category — and shows that it simultaneously captures gradient-based learners (deep nets), open games, and Bayesian agents.

## Key Contribution

`Para(C)` builds a new category whose morphisms are pairs $(P, f)$ where $P$ is a parameter object and $f$ is a $C$-morphism using $P$. Specializing $C$ to an optic category gives a setting general enough to host: gradient learners (parameters = weights, optic = lens for forward/backward pass), open games (parameters = strategies, optic = play/payoff lens), and active-inference agents. This is the constructive content behind the claim that categorical cybernetics is a unified foundation for goal-directed compositional systems.

## Vault Relevance

Anchor source for [[concepts/category-theory/categorical-cybernetics]]; generalizes [[sources/papers/ghani-hedges-compositional-game-theory-2018|compositional game theory]] and [[sources/papers/fong-spivak-tuyeras-backprop-functor-2019|backprop as functor]]. Connects to [[matteo-capucci]], [[bruno-gavranovic]], [[jules-hedges]].
