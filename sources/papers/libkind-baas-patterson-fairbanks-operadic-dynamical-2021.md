---
type: source-paper
title: "Operadic Modeling of Dynamical Systems: Mathematics and Computation"
author: [sophie-libkind, andrew-baas, evan-patterson, james-fairbanks]
year: 2021
status: queued
domain: category-theory
related_domains: [dynamics, computation]
key_concepts: [operads, wiring-diagrams, open-dynamical-systems, algebraic-julia, compositional-modeling]
---

# Operadic Modeling of Dynamical Systems: Mathematics and Computation — Libkind, Baas, Patterson & Fairbanks (2021)

> Predecessor to the 2022 structured-epidemic paper. Develops the operadic / wiring-diagram approach to compositional dynamical systems modelling and gives a computational realization in AlgebraicJulia — establishing the pipeline that the 2022 epidemic paper then applies to compartmental epidemiology.

## Key Contribution

Brings the Vagner–Spivak–Lerman wiring-diagrams-as-operad picture into working software (AlgebraicDynamics.jl / AlgebraicPetri.jl built on top of Catlab.jl), demonstrating that arbitrary open dynamical systems can be composed via operadic wiring diagrams in code, not just in theory. The "math and computation" framing is deliberate: this paper closes the loop between the categorical formalism (Spivak 2013; Vagner–Spivak–Lerman 2015) and runnable simulation.

## Vault Relevance

Bridges [[sources/papers/spivak-operad-wiring-diagrams-2013]] and [[sources/papers/vagner-spivak-lerman-open-dynamical-2015]] to the working AlgebraicJulia stack; immediate predecessor of [[sources/papers/libkind-structured-epidemic-2022]]. Cited in [[concepts/category-theory/open-systems]] and [[concepts/category-theory/wiring-diagrams]]. Connects to [[sophie-libkind]], [[andrew-baas]], [[evan-patterson]], [[james-fairbanks]].
