---
type: concept
domain: dynamics
related_domains: [computation, information]
provenance: mixed
status: developing
relates_to:
  - target: chaos-theory
    relation: measured-by
  - target: attractors
    relation: overlaps
  - target: concepts/complexity/edge-of-chaos
    relation: foundation-for
  - target: concepts/information/shannon-entropy
    relation: overlaps
tags: [Lyapunov, chaos, divergence, stability, KS-entropy]
---

# Lyapunov Exponents

> The quantitative measure of chaos: the average rate at which nearby trajectories in phase space diverge, characterizing the degree of sensitivity to initial conditions. Positive largest Lyapunov exponent = chaotic system.

## Orientation

Lyapunov exponents transform the qualitative description of chaos (sensitive dependence on initial conditions) into a quantitative one. They are computable from time series data, making them the primary empirical tool for detecting chaos in real systems. They also connect dynamical systems theory directly to information theory through their relationship to entropy production.

## Core

### Definition

For a dynamical system, consider two nearby trajectories starting at x₀ and x₀ + δ₀. Over time, their separation evolves. If the separation grows exponentially on average — ||δ(t)|| ~ ||δ₀|| e^{λt} — then λ is the (largest) Lyapunov exponent.

A system with n degrees of freedom has n Lyapunov exponents (the Lyapunov spectrum), characterizing divergence rates in each dimension of phase space. The **largest Lyapunov exponent** λ₁ is the most important:

- λ₁ < 0: trajectories converge — stable fixed point or limit cycle
- λ₁ = 0: neutral stability — on the edge, marginal
- λ₁ > 0: trajectories diverge — chaos

The magnitude of λ₁ gives the timescale of predictability. A positive Lyapunov exponent of 1 bit/second means that initial condition errors double every second — prediction horizon is on the order of 1/λ₁.

### Connection to Entropy

The **Kolmogorov-Sinai (KS) entropy** of a dynamical system — the rate at which the system generates information — equals the sum of positive Lyapunov exponents (Pesin's theorem):

```
h_KS = Σ_{λᵢ > 0} λᵢ
```

This connects the dynamical characterization of chaos to the information-theoretic one: chaotic systems generate information at a rate equal to their entropy production. Predictability is lost at exactly the rate that information is generated.

### Neural Network Application

The Jacobian of a neural network at a given input maps perturbations forward through the network. Its singular values determine whether perturbations amplify or decay. The largest Lyapunov exponent of the gradient flow during training — tracking how perturbations in weight space propagate — is the basis for the edge-of-chaos training hypothesis in Zhang et al. (2021).

Networks with λ₁ > 0 (chaotic training dynamics) suffer from exploding gradients. Networks with λ₁ < 0 (ordered training dynamics) suffer from vanishing gradients. The productive regime is λ₁ ≈ 0 — criticality — where gradients neither explode nor vanish. This is why residual connections and layer normalization work: they implement architectural constraints that keep the effective Lyapunov exponent near zero.

## Connections

**Chaos theory** (`concepts/dynamics/chaos-theory.md`) — Lyapunov exponents are the primary diagnostic for chaos; the definition of chaos is λ₁ > 0.

**Edge of chaos** (`concepts/complexity/edge-of-chaos.md`) — the edge is λ₁ ≈ 0; Lyapunov exponents give this the sharpest quantitative definition.

**Shannon entropy** (`concepts/information/shannon-entropy.md`) — connected via Pesin's theorem; KS entropy = sum of positive Lyapunov exponents.

**Neural networks** (`concepts/computation/neural-networks.md`) — the vanishing/exploding gradient problem is a Lyapunov exponent problem in disguise.

## Sources

- `sources/books/strogatz-nonlinear-dynamics-1994.md`
- `sources/papers/zhang-edge-of-chaos-nn-2021.md`

## Open Questions

- Can Lyapunov exponents be meaningfully defined for transformer architectures, where the "dynamics" are across depth rather than time?
- What is the relationship between the Lyapunov spectrum of a trained neural network and its generalization behavior?
