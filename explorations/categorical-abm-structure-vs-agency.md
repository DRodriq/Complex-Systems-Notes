---
type: exploration
name: "Categorical ABM: Structural Change vs. Agency"
domain: category-theory
related_domains: [complexity, computation, dynamics]
status: open
provenance: literature
question: "Is the agent-based-modeling / category-theory crossover primarily split between a structural-change paradigm (graph rewriting on ACSets) and an agency paradigm (Para(Optic) / optics), and is that split fundamental or an artifact of missing composition tooling?"
---

# Exploration — Categorical ABM: Structural Change vs. Agency

> **Open question.** Two categorical technologies touch agent-based modeling from different directions: **graph rewriting** on attributed C-sets (the AlgebraicJulia line), which formalizes how a system's *structure* changes, and **`Para(Optic)` / optics** (the categorical-cybernetics line), which formalizes what makes a subsystem an *agent*. Are these (a) rival formalizations of the same thing, (b) complementary layers of one model, or (c) instances of two distinct categorical paradigms that have not yet been composed? A related sub-question: in the *inclusion* sense — "ABM as a special case of a categorical construction" — which framing subsumes the whole model and which subsumes only the agent?

This note is an index into the question: a reading progression toward it, the sources and lineages on each side, and the open sub-threads. It does not answer the question.

## What is being compared

The question turns on what each formalism takes as its object.

- **Structural-change framing.** A model's state is a typed structure (an ACSet); the model evolves by firing rewrite rules. Agents are entities in the structure; behavior, birth, death, and rewiring are rule applications. Entry concept: [[concepts/category-theory/applied-category-theory]] (the AlgebraicJulia stack) and [[concepts/complexity/agent-based-modeling]].
- **Agency framing.** A model's agent is a bidirectional process — a lens / `Para(Optic)` morphism — whose backward pass carries an objective (best-response, gradient, or Bayesian inversion). Entry concept: [[concepts/category-theory/categorical-cybernetics]] and [[concepts/category-theory/lenses-and-optics]].
- **Two further framings the binary leaves out**, included here because the question cannot be posed cleanly without them:
  - **Composition / interface framing** — how subsystems plug together: [[concepts/category-theory/wiring-diagrams]], [[concepts/category-theory/polynomial-functors]], [[concepts/category-theory/open-systems]].
  - **Unification framing** — a single substrate proposed to host all of the above: [[concepts/category-theory/categorical-systems-theory]].

## Reading progression

Ordered to build from the shared substrate, up each lineage separately, then into the constructions that would bridge them. Each item notes only what it establishes for the question.

### Stage 0 — Shared substrate (both framings assume this)

1. [[sources/papers/lawvere-functorial-semantics-1963]] — syntax as a category, semantics as a functor; the move both framings inherit.
2. [[concepts/category-theory/open-systems]] → [[sources/papers/vagner-spivak-lerman-open-dynamical-2015]] — systems with boundaries that compose; the notion of an "open" subsystem both sides build on.
3. [[concepts/category-theory/generative-effects]] — a functor failing to preserve joins; the formal site where composed behavior exceeds composed structure (the reason ABM is run rather than solved).

### Stage 1 — Structural-change line

4. [[sources/papers/patterson-categorical-data-structures-2022]] — ACSets: "schema = category, state = functor"; the data structure a model's configuration lives in.
5. [[sources/papers/brown-categorical-rewriting-2023]] — DPO/SPO/SqPO rewriting on ACSets; structural change as a lawful categorical operation.
6. [[sources/software/algebraicabms-jl]] — the rewriting engine instantiated as an ABM framework (stochastic rule firing). The point at which "ABM" becomes a special case of categorical rewriting.

### Stage 2 — Agency line

7. [[sources/papers/riley-categories-optics-2018]] — optics as composable bidirectional `(get, put)` processes; the substrate of the agency framing.
8. [[sources/papers/capucci-categorical-cybernetics-2021]] — the `Para(Optic)` construction unifying games, learners, and agents under one object.
9. [[sources/papers/fong-spivak-tuyeras-backprop-functor-2019]] → [[sources/papers/cruttwell-gradient-based-learning-2022]] — the gradient-learning instance (backward pass = gradient).
10. [[sources/papers/ghani-hedges-compositional-game-theory-2018]] — the game instance (backward pass = best-response).
11. [[sources/papers/hedges-rl-categorical-cybernetics-2024]] — the RL instance (backward pass = value update).
12. [[sources/papers/smithe-bayesian-brain-2023]] → [[sources/papers/smithe-structured-active-inference-2024]] — the active-inference instance, and the first construction that places agents *on* categorical systems theory rather than in a separate optic setting.

### Stage 3 — Composition / interface doctrines (where world and agent would plug together)

13. [[sources/papers/spivak-operad-wiring-diagrams-2013]] — boxes-and-wires as an operad; composition by shared boundary.
14. [[sources/papers/libkind-baas-patterson-fairbanks-operadic-dynamical-2021]] — operadic composition of open dynamical systems in code (AlgebraicDynamics); the continuous-dynamics layer that is neither rewriting nor optic.
15. [[sources/books/spivak-niu-polynomial-functors-2021]] — `Poly`: mode-dependent interfaces; the construction for state-dependent action sets.

### Stage 4 — Unification bid (would dissolve or confirm the split)

16. [[sources/papers/myers-double-categories-dynamical-2021]] — open dynamical systems and their maps as a double category; the originating move toward one frame.
17. [[sources/books/myers-categorical-systems-theory-draft]] → [[sources/papers/myers-libkind-double-operadic-systems-2025]] — the proposed single substrate ("all the same kind of arrow").
18. [[sources/papers/dalrymple-safeguarded-ai-2024]] + [[sources/papers/dalrymple-guaranteed-safe-ai-2024]] — the funded application (DCST for Safeguarded AI) where structure + agency + verification are posed together.

## Lineages

The two framings are developed largely by two communities; a third construction sits at the proposed junction.

- **Structural / rewriting** — the AlgebraicJulia ecosystem around [[institutions/topos-institute]] and the University of Florida group: [[kris-brown]], [[evan-patterson]], [[james-fairbanks]]. Software-first; discrete structural change; running code ([[sources/software/algebraicabms-jl]]).
- **Agency / optics** — the categorical-cybernetics community around the [[institutions/cybernetics-institute]] (Strathclyde / Glasgow): [[jules-hedges]], [[matteo-capucci]], with [[toby-st-clere-smithe]] on the active-inference side. Theory-first; the mathematical structure of learning, games, and inference.
- **Junction** — [[david-jaz-myers]] and [[sophie-libkind]] (categorical systems theory / double-operadic unification), and [[david-dalrymple]] (the Safeguarded-AI program that funds DCST as a structure-and-agency substrate).

## Open sub-threads

Neutral prompts the reading progression is meant to inform — none resolved here.

- **Composition gap.** Does any current construction compose a `Para(Optic)` agent with a rewriting / Petri / ODE subsystem in one system? If not, how much of the apparent split is the absence of that operator rather than a difference of kind? (Bears on stages 2–4; see the same-substrate claim in [[sources/papers/smithe-structured-active-inference-2024]] and the unification bid in [[sources/papers/myers-libkind-double-operadic-systems-2025]].)
- **Layer vs. paradigm.** Is "ABM-as-rewriting" and "agent-as-optic" a difference of *layer* (structure beneath, agency above, vertically composed: an optic decides → a rewrite fires) or of *paradigm* (objects-transformed vs. morphisms-that-compose)?
- **Where dynamics sit.** Open dynamical systems composition (stage 3, item 14) is neither rewriting nor optic. Does its presence make the question three-way rather than two-way?
- **Inclusion asymmetry.** Under rewriting, a model *is* a rewriting system (whole-model inclusion). Under `Para(Optic)`, the *agent* is an optic but the population/structure is not. Is this asymmetry essential, or removed once a composition operator exists?
- **Subsumption claim.** Does [[concepts/category-theory/categorical-systems-theory]] demonstrably subsume both rewriting and optics as doctrines, or is that stated as a target? (Distinguish what [[sources/papers/myers-libkind-double-operadic-systems-2025]] proves from what the Safeguarded-AI program proposes to build.)

## Entry points

- Domain map: [[concepts/category-theory/INDEX]]
- The two anchor concepts: [[concepts/category-theory/applied-category-theory]] · [[concepts/category-theory/categorical-cybernetics]]
- The unification thread: [[concepts/category-theory/categorical-systems-theory]]
- The empirical method this question is about: [[concepts/complexity/agent-based-modeling]]
