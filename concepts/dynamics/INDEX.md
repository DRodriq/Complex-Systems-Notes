---
type: domain-index
domain: dynamics
status: developing
---

# Nonlinear Dynamics Domain

> The mathematical study of systems that evolve over time according to rules that are not linear — systems where outputs are not proportional to inputs, where small changes can have large effects, and where long-term behavior can be extraordinarily complex even from simple rules.

*Vault editorial stance and scope decisions: [[synthesis/why-complexity]].*

## What This Domain Covers

Nonlinear dynamics provides the mathematical backbone for much of complexity science. Chaos theory — the most publicly visible part of this domain — established that deterministic systems could produce behavior so sensitive to initial conditions as to be practically unpredictable. But the domain is broader: it includes the full toolkit of dynamical systems theory (fixed points, limit cycles, strange attractors, bifurcations, Lyapunov exponents) and its applications across physics, biology, chemistry, and engineering.

For this vault, nonlinear dynamics serves primarily as the mathematical substrate underlying complex systems. Chaos and bifurcation theory explain why CAS exhibit phase transitions and sensitive dependence. Attractors describe the long-run behavior that systems settle into. Lyapunov exponents give a quantitative handle on chaos.

## Core Concepts

| Concept | One-line description | Status |
|---|---|---|
| [[chaos-theory]] | Deterministic unpredictability from sensitive dependence on initial conditions | developing |
| [[attractors]] | The geometric objects that long-run trajectories converge to: fixed points, limit cycles, strange attractors | developing |
| [[bifurcation]] | Qualitative change in a system's behavior as a parameter crosses a threshold | developing |
| [[lyapunov-exponents]] | Quantitative measure of how fast nearby trajectories diverge — the chaos diagnostic | developing |
| [[phase-space]] | The abstract space in which all possible states of a system live; trajectories are paths through it | stub |
| [[limit-cycles]] | Periodic attractors — the system settles into stable oscillation — see attractors.md | stub |
| [[manifold-hypothesis]] | High-dimensional data lies near a low-dimensional manifold; intrinsic dimensionality governs geometry | stub |
| [[persistent-homology]] | TDA method that tracks topological features (components, loops, voids) across all scales simultaneously | stub |
| [[takens-embedding]] | Reconstructing a dynamical attractor's geometry from a scalar time series via delay coordinates | stub |

## Connections to Other Domains

- **Complexity**: The edge of chaos is a dynamical systems concept applied to CAS. Emergence and self-organization often involve phase transitions that bifurcation theory describes.
- **Computation**: Neural networks are dynamical systems — their training and inference can be analyzed using these tools. The edge of chaos hypothesis is specifically a dynamical framing of optimal computation.
- **Information**: Lyapunov exponents connect to information production; chaotic systems generate information at a measurable rate.
- **Applied/Ecology**: Predator-prey models, population dynamics, and epidemiological models are all nonlinear dynamical systems.

## Key Figures

[[Steven Strogatz]] · [[Edward Norton Lorenz]] · [[Doyne Farmer]] · [[Jurgen Kurths]] · [[Aleksandr Lyapunov]]

## Key Sources

- `sources/books/strogatz-nonlinear-dynamics-1994.md` — the standard introduction; applications across biology, chemistry, physics, engineering
- `sources/books/gleick-chaos-1987.md` — narrative history; best popular account of the field's emergence
- `sources/books/hirsch-devaney-smale-2003.md` — rigorous mathematical treatment
- `sources/books/wiggins-1990.md` — applied nonlinear dynamics for scientists and engineers
