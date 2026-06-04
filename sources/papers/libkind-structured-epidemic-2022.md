---
type: source-paper
title: "An Algebraic Framework for Structured Epidemic Modelling"
author: [sophie-libkind, andrew-baas, micah-halter, evan-patterson, james-fairbanks]
year: 2022
status: queued
domain: category-theory
related_domains: [applied, dynamics]
key_concepts: [typed-petri-nets, stratification, typed-product, compositional-epidemic-modeling]
---

# An Algebraic Framework for Structured Epidemic Modelling — Libkind et al. (2022)

> Phil. Trans. R. Soc. A (arXiv:2203.16345). Introduces **typed Petri nets**, **`oapply_typed`**, and **stratification via `typed_product`** — the operational machinery that makes compositional epidemic modelling practical.

## Key Contribution

Demonstrates that structured cospans + typed Petri nets give a workable substrate for assembling epidemiological models from primitive parts (disease dynamics, age structure, geography, vaccination) via type-respecting composition. `typed_product` lets you build, say, "spatial × age-stratified × multi-strain" models by composing each factor separately and stratifying — a major reduction in the bookkeeping cost of compartmental modelling at scale.

## Vault Relevance

Anchors the practical substrate underneath [[concepts/category-theory/open-systems]] and [[concepts/category-theory/wiring-diagrams]] in real modelling. Connects to [[sophie-libkind]], [[evan-patterson]], [[james-fairbanks]].
