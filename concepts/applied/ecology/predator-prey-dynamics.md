---
type: concept
domain: applied
related_domains: [dynamics]
provenance: mixed
status: developing
relates_to:
  - target: concepts/dynamics/attractors
    relation: instance-of
  - target: concepts/dynamics/bifurcation
    relation: overlaps
  - target: concepts/dynamics/chaos-theory
    relation: overlaps
tags: [predator-prey, Lotka-Volterra, population-dynamics, limit-cycles, chaos-ecology]
---

# Predator-Prey Dynamics

> The canonical nonlinear ecological interaction: oscillating populations of consumers and resources, modeled by the Lotka-Volterra equations, exhibiting limit cycles, chaos, and multiple coexistence mechanisms depending on functional form and environmental structure.

## Orientation

Predator-prey systems are the workhorse of theoretical ecology and one of the richest application domains for nonlinear dynamics. The Lotka-Volterra equations are among the first nonlinear dynamical systems studied systematically, and their subsequent generalizations have produced nearly every class of complex dynamical behavior — limit cycles, chaos, bistability, bifurcations — in ecological contexts.

For this vault, predator-prey dynamics matter both as an application domain for dynamical systems tools and as one of the primary empirical systems where complexity science has connected theory to data.

## Core

### Lotka-Volterra

The basic predator-prey system:

```
dN/dt = rN - aNP     (prey: grow at rate r, die at rate a per predator P)
dP/dt = baNP - mP    (predator: gain from prey, die at rate m)
```

This produces **neutral cycles** — closed orbits in phase space whose amplitude depends on initial conditions. The system is neutrally stable — not asymptotically stable (perturbations don't decay) and not unstable (perturbations don't grow). This is a degenerate case that disappears with more realistic modeling.

### Rosenzweig-MacArthur and Limit Cycles

Adding logistic growth for the prey and a saturating (Type II) functional response for the predator produces the Rosenzweig-MacArthur model, which is far more realistic and far richer. Key result: as prey carrying capacity increases, the system undergoes a Hopf bifurcation from a stable equilibrium to a stable limit cycle — **paradox of enrichment**. Enriching the prey's environment (adding nutrients) destabilizes the system, potentially driving it to extinction through large oscillations.

This was one of the first theoretical predictions in ecology that was qualitatively verified empirically, establishing the relevance of nonlinear dynamics to real population dynamics.

### Chaos in Ecological Systems

At higher complexity — additional trophic levels, spatial structure, stochasticity — ecological models produce chaos. May's 1974 paper showed that even simple single-species difference equations (discrete-time logistic map) exhibit chaos for high growth rates. This was consequential: it meant that ecological variability might reflect deterministic chaos rather than environmental noise, and that long-term population prediction might be fundamentally limited.

The empirical detection of chaos in real ecological time series has been contentious — distinguishing chaos from noise requires long, high-quality data. Sugihara and May's empirical nonlinear forecasting methods (1990) provided tools for this. The question remains active.

### Parasitism and Complexity

The vault has papers extending predator-prey dynamics to parasitism — consumer-resource interactions where the consumer does not kill the host immediately but modifies its fitness and may castrate or modify behavior. Parasites add a third trophic level with its own dynamics. Hall, Duffy, and Caceres (2005) in the vault is an example of empirical work on predator-prey-parasite systems producing complex dynamics including limit cycles and chaotic behavior.

## Connections

**Attractors** (`concepts/dynamics/attractors.md`) — the Rosenzweig-MacArthur limit cycle is a Hopf bifurcation product; predator-prey dynamics are studied as attractor geometry.

**Bifurcation** (`concepts/dynamics/bifurcation.md`) — the paradox of enrichment is a Hopf bifurcation; chaos in ecological models arises through period-doubling cascades.

**Chaos theory** (`concepts/dynamics/chaos-theory.md`) — ecological systems were among the first biological application domains for chaos theory; May's 1974 paper is foundational.

**Ecology INDEX** (`concepts/applied/ecology/INDEX.md`)

## Sources

- `sources/papers/hall-duffy-caceres-predator-prey-2005.md`
- `sources/books/strogatz-nonlinear-dynamics-1994.md` — Chapter 6 covers Lotka-Volterra and extensions thoroughly
- `sources/books/hastings-population-biology-1997.md`

## Open Questions

- Is chaos genuinely present in empirical population time series, or are observed fluctuations better explained by environmental stochasticity?
- What determines whether a food web is stable — high connectance tends to destabilize in May's random matrix models, but real food webs are highly connected and stable. What structural features (compartmentalization, weak links) provide stability?
