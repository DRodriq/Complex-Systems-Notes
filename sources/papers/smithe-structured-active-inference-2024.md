---
type: source-paper
title: "Structured Active Inference"
author: [toby-st-clere-smithe]
year: 2024
status: queued
domain: category-theory
related_domains: [computation, complexity, philosophy]
key_concepts: [active-inference, categorical-systems-theory, markov-blanket, agents, meta-agents, mode-dependence, generative-models]
---

# Structured Active Inference — Smithe (2024)

> arXiv:2406.07577 (ACT 2024 extended abstract). A large generalization and formalization of active inference using **categorical systems theory**. Generative models are cast formally as *systems on an interface* — a compositional abstraction of the Markov blanket — and agents are **"controllers" for their generative models, formally dual to them**.

## Key Contribution

Smithe rebuilds Karl Friston's active-inference / free-energy framework on the double-categorical-systems-theory substrate. The central reframing: a generative model is a system *on an interface*, where the interface generalizes the Markov blanket into a compositional boundary; the agent is then the dual *controller* of that model. Because the interface is a first-class structured object, the framework opens directions that flat active inference could not express:

- **agents with structured / mode-dependent interfaces** — e.g. agents whose available actions depend on context, or that interact with computer APIs;
- **agents that manage other agents** — compositional multi-agent structure;
- **meta-agents** — agents that use active inference to change their own (internal or external) structure.

This is the most "agent-native" instance of the categorical-cybernetics program: perception is the forward pass, inference/free-energy-minimization is the backward (selection) pass, and the agent/world boundary is a chosen factorization (Markov blanket), not an ontological seam.

## Vault Relevance

Primary current source for the **agent** side of [[concepts/category-theory/categorical-cybernetics]] and a direct application of [[concepts/category-theory/categorical-systems-theory]]. The mode-dependent interfaces connect to [[concepts/category-theory/polynomial-functors]]; the perceive/act duality to [[concepts/category-theory/lenses-and-optics]]. Supersedes the earlier Bayesian-lenses framing in [[sources/papers/smithe-bayesian-brain-2023]]. Connects to [[toby-st-clere-smithe]] and [[karl-friston]]. The meta-agent / self-restructuring theme links to open-ended structural dynamics (graph rewriting) discussed under [[concepts/complexity/agent-based-modeling]].
