---
type: concept
name: "Categorical Systems Theory"
domain: category-theory
related_domains: [dynamics, computation, complexity]
status: developing
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Categorical Systems Theory

> A double-categorical framework, developed by David Jaz Myers in an ongoing book draft, aimed at unifying the many existing categorical treatments of open dynamical systems — continuous, discrete, stochastic, deterministic — under a single composition framework. The double-category structure separates "systems and their behaviours" from "system maps that respect interfaces," giving a vocabulary in which results from different communities (open Petri nets, open dynamical systems on wiring diagrams, polynomial-functor interactive systems) can be compared and combined.

## Orientation

By the late 2010s, several distinct categorical approaches to open systems had matured — structured/decorated cospans, the operad of wiring diagrams, the category Poly of polynomial functors — each with its own community, vocabulary, and intended applications. Myers' *Categorical Systems Theory* (in progress) attempts a unifying double-categorical synthesis, treating systems and the maps between them as a coherent two-dimensional structure. The work is widely cited and circulated in draft form within the ACT community.

## Core

(stub — to be filled when this node develops)

## Connections

- Generalizes [[open-systems]] (structured cospans, open Petri nets) and the [[wiring-diagrams|wiring-diagram]] approach into a common framework.
- Closely related to [[polynomial-functors]] — Poly is one of the categories that Myers' framework can be instantiated against.
- A point of contact between [[applied-category-theory]] and classical [[concepts/dynamics/INDEX|dynamical systems]] thinking.
- The substrate beneath structured agents: [[sources/papers/smithe-structured-active-inference-2024]] builds active-inference agents directly on categorical systems theory.

### Recent consolidation (2025)

The programme has progressed from the book draft toward a unified formal core:
- [[sources/papers/myers-libkind-double-operadic-systems-2025]] packages systems, their interactions, and their maps into one double-operadic structure (a symmetric monoidal loose right module over a double category) — the "single substrate" step.
- [[sources/papers/myers-nondeterministic-behaviours-dcst-2025]] develops the behaviour side for nondeterministic systems.
- Applied uptake: a funded **"Double Categorical Systems Theory for Safeguarded AI"** project uses DCST as a mathematical foundation for AI system design and safety — the theory track of [[david-dalrymple|Dalrymple]]'s ARIA programme ([[sources/papers/dalrymple-safeguarded-ai-2024]], [[sources/papers/dalrymple-guaranteed-safe-ai-2024]]).

## Sources

- [[sources/books/myers-categorical-systems-theory-draft]] — *Categorical Systems Theory* (book draft, ongoing).
- [[sources/papers/myers-double-categories-dynamical-2021]] — *Double Categories of Open Dynamical Systems*; the originating research paper behind the book draft.
- [[sources/papers/myers-libkind-double-operadic-systems-2025]] — double-operadic unification (2025); the current anchor.
- [[sources/papers/myers-nondeterministic-behaviours-dcst-2025]] — nondeterministic behaviours in DCST (2025).
- [[sources/papers/vagner-spivak-lerman-open-dynamical-2015]] — earlier wiring-diagrams approach that the double-categorical framework generalizes.
- [[sources/papers/baez-courser-structured-cospans-2020]] — structured cospans, one of the key categorical structures Myers' framework subsumes.
