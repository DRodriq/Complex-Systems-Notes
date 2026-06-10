---
type: concept
name: "Categorical Cybernetics"
domain: category-theory
related_domains: [computation, complexity, philosophy]
status: developing
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Categorical Cybernetics

> An emerging research programme — anchored by the 2021 ACT paper *Towards Foundations of Categorical Cybernetics* (Capucci, Gavranović, Hedges, Rischel) — that uses categorical machinery to give a unified compositional account of **goal-directed, feedback-controlled, learning, and perceiving systems**. The central construction is `Para(Optic)`, which simultaneously captures gradient-based learners (deep nets), open games, and Bayesian agents within a single categorical setting.

## Orientation

Cybernetics — the science of control and communication in animal and machine — was a 1940s–60s programme (Wiener, Ashby, Bateson) that fragmented into AI, control theory, and systems biology without consolidating its central object. Categorical cybernetics is an attempt to give it that consolidation: the `Para(Optic)` construction (parameterized morphisms over an optic category) is general enough to host gradient descent, open games, and active-inference agents as special cases, suggesting these phenomena share more than informal resemblance.

## Core

(stub — to be filled when this node develops)

## Connections

- Builds on [[lenses-and-optics]] (specifically the optic construction) as the bidirectional substrate.
- Generalizes [[compositional-game-theory]] (open games arise as one slice of `Para(Optic)`) and the *Backprop as Functor* construction (gradient learning is another).
- Connects to [[polynomial-functors]] via the active-inference / interactive-systems frontier.
- A re-foundation attempt for [[concepts/dynamics/INDEX|dynamical systems]] thinking about agents, complementing rather than displacing classical control-theoretic accounts.
- Community organized via the [[institutions/cybernetics-institute]] (UK).

### Recent frontier (2024–2026)

The programme has moved from foundations to applied agents and AI. Key developments:
- **Reinforcement learning** enters `Para(Optic)`: [[sources/papers/hedges-rl-categorical-cybernetics-2024]] (with the companion result that value iteration is optic composition — Bellman backup = precomposition with an optic). The backward pass *is* the value update.
- **Active inference**, restructured: [[sources/papers/smithe-structured-active-inference-2024]] casts agents as controllers dual to their generative models, with mode-dependent interfaces, agents-managing-agents, and self-restructuring meta-agents.
- **Frontier (2026)**: [[sources/papers/agent-policies-higher-order-causal-2026]] — reward-seeking agent policies via higher-order causal functions.
- **Into mainstream ML**: [[sources/papers/cruttwell-gradient-based-learning-2022]] gives the full parametric-lens anatomy of gradient learning (network, loss, optimiser, update as modular components), and [[sources/papers/gavranovic-categorical-deep-learning-2024]] argues *all* neural architectures are categorically describable — the bridge from `Para(Optic)` to architecture design the ML field can test.

## Sources

- [[sources/papers/capucci-categorical-cybernetics-2021]] — *Towards Foundations of Categorical Cybernetics*; the `Para(Optic)` construction.
- [[sources/papers/fong-spivak-tuyeras-backprop-functor-2019]] — *Backprop as Functor*; learning as compositional, prefiguring `Para(Optic)`.
- [[sources/papers/cruttwell-gradient-based-learning-2022]] — *Categorical Foundations of Gradient-Based Learning*; the parametric-lens anatomy of deep learning (the missing middle between Backprop-as-Functor and RL-in-cybernetics).
- [[sources/papers/gavranovic-categorical-deep-learning-2024]] — *Categorical Deep Learning*; architectures as (co)monad algebras; the ACT-to-mainstream-ML bridge.
- [[sources/papers/ghani-hedges-compositional-game-theory-2018]] — *Compositional Game Theory*; open games, a sibling construction.
- [[sources/papers/hedges-rl-categorical-cybernetics-2024]] — RL inside `Para(Optic)`; value iteration as optic composition.
- [[sources/papers/smithe-structured-active-inference-2024]] — structured active inference; agents as duals of generative models; meta-agents.
- [[sources/papers/agent-policies-higher-order-causal-2026]] — higher-order causal functions for reward-seeking agents (early 2026).
- [[sources/papers/smithe-bayesian-brain-2023]] — earlier categorical active inference; agents with internal models.
