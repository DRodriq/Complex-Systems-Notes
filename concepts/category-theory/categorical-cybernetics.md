---
type: concept
name: "Categorical Cybernetics"
domain: category-theory
related_domains: [computation, complexity, philosophy]
status: stub
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

## Sources

- [[sources/papers/capucci-categorical-cybernetics-2021]] — *Towards Foundations of Categorical Cybernetics*; the `Para(Optic)` construction.
- [[sources/papers/fong-spivak-tuyeras-backprop-functor-2019]] — *Backprop as Functor*; learning as compositional, prefiguring `Para(Optic)`.
- [[sources/papers/ghani-hedges-compositional-game-theory-2018]] — *Compositional Game Theory*; open games, a sibling construction.
- [[sources/papers/smithe-bayesian-brain-2023]] — categorical active inference; agents with internal models.
