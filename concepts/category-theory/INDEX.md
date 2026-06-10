---
type: domain-index
domain: category-theory
related_domains: [computation, complexity, dynamics, philosophy]
status: developing
---

# Category Theory Domain

> The mathematics of composition: objects, morphisms, functors, and the structures that result when "how things compose" is taken as primary. Pure category theory is the foundational layer; applied category theory (ACT) is the active research front bringing categorical tools to dynamical systems, computation, games, learning, and cybernetics.

*Vault editorial stance and scope decisions: [[synthesis/why-complexity]].*

## What This Domain Covers

This domain indexes the categorical-thinking cluster relevant to complexity science: applied category theory (Fong & Spivak's *Seven Sketches* line), structured cospans and open systems (Baez and collaborators), wiring diagrams as operads (Spivak), polynomial functors as a theory of interaction (Spivak & Niu), compositional game theory (Hedges and collaborators), lenses and optics (Riley), categorical cybernetics (Capucci, Gavranović, Hedges, Rischel), and categorical systems theory (Myers).

The unifying idea: complex systems are built by composing simpler ones, and categorical machinery makes that composition lawful and scalable. The vault uses these tools as the formal substrate underneath compositional modelling (see e.g. [[concepts/complexity/agent-based-modeling]] for the empirical-modelling counterpart, and [[concepts/geometry/discrete-exterior-calculus]] for the differential-operator layer carried into multiphysics via Decapodes).

## Core Topics

| Topic | One-line description | Status |
|---|---|---|
| [[applied-category-theory]] | The umbrella term for the broader programme; *Seven Sketches* as its canonical introduction | stub |
| [[functorial-semantics]] | Lawvere's framing: syntax is a category, semantics is a functor | stub |
| [[open-systems]] | Structured cospans, decorated cospans, open Petri nets — systems with boundaries that compose | stub |
| [[wiring-diagrams]] | Boxes-and-wires as an operad; systems-in-boxes as algebras over it | stub |
| [[polynomial-functors]] | `Poly` — mathematical theory of interaction; open interactive dynamical systems with mode-dependent interfaces | developing |
| [[lenses-and-optics]] | Bidirectional `(get, put)` processes; the substrate for compositional agents and learners | stub |
| [[generative-effects]] | The precise term (Fong & Spivak) for a functor failing to preserve joins/colimits — emergence formalized | stub |
| [[compositional-game-theory]] | Open games — agents-with-strategies built from lenses; Ghani–Hedges–Winschel–Zahn line | stub |
| [[categorical-cybernetics]] | `Para(Optic)` and related constructions unifying games, learners, and agents | developing |
| [[categorical-systems-theory]] | Double-categorical framework unifying open dynamical systems and their composition (Myers) | developing |

## Key Figures

[[david-spivak]] · [[brendan-fong]] · [[john-baez]] · [[jules-hedges]] · [[evan-patterson]] · [[james-fairbanks]] · [[david-jaz-myers]] · [[sophie-libkind]] · [[toby-st-clere-smithe]] · [[william-lawvere]] · [[matteo-capucci]] · [[bruno-gavranovic]] · [[geoffrey-cruttwell]] · [[kris-brown]] · [[petar-velickovic]] · [[david-dalrymple]]

## Key Sources

- [[sources/books/fong-spivak-seven-sketches-2018]] — accessible entry point
- [[sources/books/spivak-niu-polynomial-functors-2021]] — Poly as a theory of interaction (Cambridge UP, 2025)
- [[sources/books/myers-categorical-systems-theory-draft]] — double-categorical synthesis
- [[sources/papers/baez-pollard-reaction-networks-2017]] — rate equation as a functor
- [[sources/papers/spivak-operad-wiring-diagrams-2013]] — operadic foundations
- [[sources/papers/ghani-hedges-compositional-game-theory-2018]] — open games
- [[sources/papers/libkind-baas-patterson-fairbanks-operadic-dynamical-2021]] — operadic dynamical-systems modelling in code (AlgebraicJulia)
- [[sources/papers/brown-categorical-rewriting-2023]] — DPO/SPO/SqPO rewriting for acsets; the structural-change engine under ABM-via-rewriting

## Current Frontier (2024–2026)

The field moved from foundations to applied agents, a unified systems theory, and working software:
- [[sources/papers/myers-libkind-double-operadic-systems-2025]] — double-operadic unification of systems (2025).
- [[sources/papers/smithe-structured-active-inference-2024]] — agents as duals of generative models; meta-agents.
- [[sources/papers/hedges-rl-categorical-cybernetics-2024]] — RL inside `Para(Optic)`; value iteration as optic composition.
- [[sources/papers/agent-policies-higher-order-causal-2026]] — higher-order causal functions for reward-seeking agents (2026).
- [[sources/papers/morris-decapodes-2024]] — Decapodes / AlgebraicJulia: working compositional simulation + graph-rewriting ABM.
- [[sources/papers/cruttwell-gradient-based-learning-2022]] + [[sources/papers/gavranovic-categorical-deep-learning-2024]] — the categorical-learning line reaching mainstream ML (parametric-lens learners; architectures as monad algebras).
- [[sources/papers/dalrymple-safeguarded-ai-2024]] + [[sources/papers/dalrymple-guaranteed-safe-ai-2024]] — Guaranteed-Safe / Safeguarded AI; the funded applied stake behind DCST (categorical world-models + verified typed agents).

## Open Explorations

- [[explorations/categorical-abm-structure-vs-agency]] — does the ABM / category-theory crossover split between structural rewriting and agent optics, and is that split fundamental or a missing-composition artifact? A source-indexed reading-map into the question.

## Software

The computational substrate under this cluster lives in [[sources/software/INDEX|sources/software]] — the AlgebraicJulia ecosystem (Catlab, AlgebraicDynamics, AlgebraicPetri, AlgebraicRewriting, Decapodes), plus Topos's CatColab and the Haskell open-games-engine, each annotated with maintenance status. First full node: [[sources/software/algebraicabms-jl]] (graph-rewriting ABM, research-grade).

## Key Institutions

[[institutions/topos-institute]] · [[institutions/cybernetics-institute]] · [[institutions/uc-riverside]] (Baez network-theory programme) · [[institutions/gtri]] (Decapodes applied)
