---
type: source-paper
title: "Towards Guaranteed Safe AI: A Framework for Ensuring Robust and Reliable AI Systems"
author: [david-dalrymple]
year: 2024
status: queued
domain: computation
related_domains: [category-theory, philosophy]
key_concepts: [categorical-systems-theory, world-model, formal-verification, ai-safety]
---

# Towards Guaranteed Safe AI — Dalrymple et al. (2024)

> arXiv:2405.06624. A framework paper (Dalrymple with Bengio, Russell, Tegmark, Seshia, Omohundro, and a large multi-author group) laying out **Guaranteed Safe (GS) AI**: systems whose safety rests on three components — a world-model, a safety specification, and a verifier that produces an auditable proof the AI satisfies the spec relative to the model.

## Key Contribution

This is the broad, citable statement of the agenda that [[sources/papers/dalrymple-safeguarded-ai-2024|Safeguarded AI]] funds. It formalises a spectrum of world-model and verification strength, and argues that high-stakes deployment should demand quantitative guarantees rather than test-set performance. The connection to the vault's CT cluster is the world-model + typed-policy layer: categorical world-models and interface-typed agents (the Myers/Poly/Smithe line) are one concrete way to supply the "world-model" and "verifiable policy" slots this framework leaves open. It is the bridge from the categorical machinery to a named, multi-institution AI-safety programme.

## Vault Relevance

Framework-level companion to [[sources/papers/dalrymple-safeguarded-ai-2024]]; situates [[concepts/category-theory/categorical-systems-theory]] and [[concepts/category-theory/polynomial-functors|typed interfaces]] as candidate substrate for guaranteed-safe agents. Connects to [[david-dalrymple]]. The "verifiability" rationale behind why the vault tracks the agent-as-typed-system thread at all.
