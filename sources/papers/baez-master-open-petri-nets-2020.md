---
type: source-paper
title: "Open Petri Nets"
author: [john-baez, jade-master]
year: 2020
status: queued
domain: category-theory
related_domains: [computation, dynamics]
key_concepts: [open-petri-nets, structured-cospans, compositional-modeling, reachability]
---

# Open Petri Nets — Baez & Master (2020)

> Math. Struct. Comp. Sci. (arXiv:1808.05415). Provides the categorical foundation for **open Petri nets** — Petri nets equipped with input/output places that compose along shared boundaries via the structured-cospan construction.

## Key Contribution

Open Petri nets are the categorical formalization of the engineering intuition that you should be able to wire two reaction-network/process-network fragments together along shared species. The paper develops the category of open Petri nets, proves the relevant composition laws, and provides the substrate that subsequent work (Libkind et al. 2022 on structured epidemic modelling, AlgebraicPetri.jl) builds on.

## Vault Relevance

Foundational source for [[concepts/category-theory/open-systems]]; the formal home of the open Petri nets that recur throughout compositional epidemic and reaction-network modelling. Connects to [[john-baez]] and [[jade-master]].
