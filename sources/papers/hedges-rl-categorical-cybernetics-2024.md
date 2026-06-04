---
type: source-paper
title: "Reinforcement Learning in Categorical Cybernetics"
author: [jules-hedges, riu-rodriguez-sakamoto]
year: 2024
status: queued
domain: category-theory
related_domains: [computation, complexity]
key_concepts: [reinforcement-learning, categorical-cybernetics, para-optic, open-games, value-iteration, bellman]
---

# Reinforcement Learning in Categorical Cybernetics — Hedges & Rodríguez Sakamoto (2024)

> arXiv:2404.02688 (Proceedings of Applied Category Theory 2024). Places reinforcement-learning agents inside the `Para(Optic)` framework of categorical cybernetics, showing RL shares the same compositional bidirectional structure as open games and gradient learners.

## Key Contribution

RL agents are realized as morphisms in `Para(Optic)`: the forward pass produces actions, the backward pass carries the value/credit signal, and the parameters are the policy/value function. A closely related companion result — **"Value Iteration is Optic Composition"** — shows that Bellman operators are representable as optics and that Bellman backup is justified as precomposition with that optic. Together these make precise the claim that *agency lives in the backward pass*: the Bellman/value-update structure is exactly the backward channel of the agent's optic. RL thus joins games (backward = best-response) and deep learning (backward = gradient) as one more instance of the same `Para(Optic)` object.

## Vault Relevance

Develops the RL instance of [[concepts/category-theory/categorical-cybernetics]]; built on [[concepts/category-theory/lenses-and-optics]] and the `Para(Optic)` construction of [[sources/papers/capucci-categorical-cybernetics-2021]]. Sibling to [[sources/papers/ghani-hedges-compositional-game-theory-2018|open games]]. Connects to [[jules-hedges]]. Relevant to the [[reinforcement-learning]] concept and to agent design in a compositional modeling lab.
