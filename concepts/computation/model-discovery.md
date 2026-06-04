---
type: concept
name: "Model Discovery"
domain: computation
related_domains: [dynamics, complexity]
status: developing
provenance: mixed
extends: []
instance_of: []
contrasts_with: []
---

# Model Discovery

> Automated search over a vast space of statistical or dynamical models, subject to domain-specific constraints. Increasingly framed as a neural-network-driven problem, where the network learns parameters (and sometimes structure) of an underlying dynamical system from observations.

## Orientation

Statistical model discovery is a search over a vast space of candidate models. Efficiently searching that space has traditionally required expertise in both modeling and the problem domain. Recent work treats this as a learning problem: neural networks (and language models, increasingly) search the model space directly. See [[sources/papers/li-automated-model-discovery-2024|Li, Fox, Goodman (2024)]].

## Core

(stub — to be filled when this node develops)

## Personal View

Consider the discrete logistic map $x_t = r \, x_{t-1}(1 - x_{t-1})$. Its bifurcation diagram exhibits the period-doubling route to chaos as $r$ increases. A neural network can in principle learn the parameter $r$ in the simple regimes and in chaos — the network can simulate the basic dynamics, the chaos, and the everything-in-between. **The everything-in-between (the edge of chaos) is what matters most.**

One framing for why complex adaptive systems live near the edge of chaos: there's a tradeoff between being extremely stable around a small portion of the solution space, versus sampling that space too broadly to retain coherence. The system wants to be stable around dynamics that work, but also wants to explore in case other regions are more fit. Chaos itself is too noisy — you're unlikely to land on a better region by accident. Frozen stasis is no better. You balance the two by being *on the edge of chaos*, sampling the solution space at the right rate.

A dynamical system at the edge of chaos can be probed by a neural-network-driven model discovery loop: small parameter perturbations let the system explore without straying too far. Positive outcomes drift the system toward that exploration; failures die off. A NN performing model discovery in this regime should evolve more efficiently than one starting from a random soup of math and weights.

There are two complementary contributions here:
1. **Human modeler** frames the broad strokes of the dynamics — reducing dimensions, giving the network a structural starting point near the actual dynamics.
2. **Neural network** fills in gaps, refines parameters, and can suggest dimensions that lead to more efficient solutions.

Done well, this should massively reduce data requirements for training and improve end performance compared to a "from scratch" NN approach.

## Connections

- Edge-of-chaos framing connects to [[concepts/computation/stat-physics-of-learning|stat-physics-of-learning]] and the broader literature on critical regimes in neural training (see [[sources/papers/zhang-edge-of-chaos-nn-2021]]).
- Related to [[concepts/computation/neural-networks|neural networks]] and dimensional reduction via [[umap]].
- Active research area: [[people/emily-fox|Emily Fox]], [[people/noah-goodman|Noah Goodman]], [[people/yuying-liu|Yuying Liu]], [[people/ellen-kuhl|Ellen Kuhl]].

## Sources

- [[sources/papers/li-automated-model-discovery-2024]] — Li, Fox, Goodman (2024). Automated statistical model discovery with LLMs.
- [[sources/papers/zhang-edge-of-chaos-nn-2021]] — Zhang et al. (2021). Edge of chaos as a guiding principle for NN training.

## Open Questions

- How much structural prior does the network need from a human modeler before model discovery becomes efficient?
- Is "edge-of-chaos" a useful regularizer for the discovery loop itself, or only for the discovered model?
- What is the right interface between human structural framing and NN parameter refinement?
