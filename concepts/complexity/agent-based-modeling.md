---
type: concept
domain: complexity
related_domains: [computation, applied]
provenance: mixed
status: developing
relates_to:
  - target: complex-adaptive-systems
    relation: used-in
  - target: concepts/computation/cellular-automata
    relation: extends
  - target: concepts/computation/reinforcement-learning
    relation: overlaps
tags: [ABM, agent-based-modeling, simulation, emergence, Epstein, ODD]
---

# Agent-Based Modeling

> A computational methodology for studying complex systems: explicitly represent individual agents with rules, simulate their local interactions, and observe what global behavior emerges — the primary empirical method of complexity science.

## Orientation

Agent-based modeling (ABM) is the computational methodology that puts the CAS framework into practice. Instead of writing equations describing the aggregate behavior of a system, you write rules for individual agents and let the collective behavior emerge from simulation. ABM is particularly suited to systems where heterogeneity, local interaction, and emergent global patterns are the phenomena of interest — which is most of what complexity science studies.

ABM occupies an unusual position in science: it is neither purely theoretical (you cannot derive results analytically) nor purely empirical (the system is simulated, not observed). It is a third mode of inquiry — computational exploration — that became viable with cheap computing.

## Core

### What Distinguishes ABM

Classical mathematical models of social or biological systems typically describe aggregate quantities — average population, mean field, representative agent. These work when individual variation is unimportant and interactions are well-mixed (random). ABM relaxes both assumptions: agents can differ from each other (heterogeneity), and they interact locally with specific neighbors (spatial or network structure).

The emergent collective behavior of an ABM is not an assumption but an output. You do not write "the population oscillates with period T" — you write agent rules and observe whether oscillation appears, when, under what conditions, and with what period. This makes ABM powerful for hypothesis testing about mechanisms.

### Epstein and Axtell: Sugarscape

The founding demonstration of modern ABM as a social science tool is Epstein and Axtell's Sugarscape model (1996). Agents inhabit a grid with sugar distributed across it; agents move toward higher sugar concentrations, harvest and consume sugar, and can trade, reproduce, and die. From these simple rules emerge: wealth distributions resembling empirical income distributions (power-law tails), trade networks, cultural formation, disease spreading, and warfare.

Sugarscape was methodologically significant because it showed that aggregate social phenomena — inequality, trade patterns, group formation — could emerge from simple individual rules without being assumed. The model is not a precise description of any real economy; it is an existence proof that emergence-from-rules is possible, and a laboratory for studying which rules produce which outcomes.

### The ODD Protocol

A persistent problem in ABM is reproducibility: two researchers implementing "the same" model from a description often produce different results. Grimm et al.'s ODD protocol (Overview, Design Concepts, Details) is a standardized description format for ABMs, covering:

- **Overview**: purpose, entities/state variables, scales
- **Design concepts**: emergence, adaptation, objectives, learning, prediction, sensing, interaction, stochasticity, collectives, observation
- **Details**: initialization, input data, submodels

ODD has become the standard for reporting ABMs in ecology and is increasingly adopted in social science and archaeology.

### Key Toolkits

The vault has notes on the main ABM platforms:

- **NetLogo** — the standard teaching and research platform; Logo-based, accessible, extensive model library
- **Mesa** — Python-based; integrates with scientific Python ecosystem (NumPy, pandas, visualization)
- **MASON** — Java-based; designed for speed and large-scale simulations
- **Repast** — Java/Python; built for social simulation, used in policy and defense modeling
- **GAMA** — spatial ABM platform with GIS integration

The choice depends on scale, language preference, and whether spatial or network structure is central.

### Relationship to CAS Theory

ABM is the empirical arm of CAS theory. CAS provides the conceptual framework (agents, schemas, niches, emergence); ABM provides the tools to instantiate and explore it. Every ABM is a CAS, but not every CAS claim requires an ABM — some are theoretical.

The connection to RL is increasingly tight: multi-agent RL systems are ABMs where agents learn rather than follow fixed rules. The distinction between classical ABM (fixed rules, study emergence) and MARL (adaptive rules, study learning dynamics and emergent strategies) is becoming a design choice rather than a categorical difference.

## Connections

**Complex adaptive systems** (`concepts/complexity/complex-adaptive-systems.md`) — CAS is the theory; ABM is the method for studying it computationally.

**Cellular automata** (`concepts/computation/cellular-automata.md`) — CAs are the simplest ABMs: cells are agents with binary states and local rules. Full ABMs generalize to heterogeneous agents with richer state and more complex rules.

**Multi-agent RL** (`concepts/computation/multi-agent-rl.md`) — MARL is ABM with learning agents; the boundary between them is the presence or absence of a gradient-based or evolutionary learning mechanism.

**Applied ecology** (`concepts/applied/ecology/INDEX.md`) — ABM is a primary tool in ecology for modeling population dynamics, landscape ecology, and evolutionary dynamics.

**Categorical ABM** (`concepts/category-theory/applied-category-theory.md`) — the AlgebraicJulia line recasts ABM as *typed graph rewriting*: agents and world are an acset, and births/deaths/rewirings are double-pushout rules, so structural change stays correct-by-construction. Theory in `sources/papers/brown-categorical-rewriting-2023.md`; implementation in `sources/software/algebraicabms-jl.md` (research-grade).

## Sources

- `sources/books/agent-based-modeling-archaeology-2021.md`
- `sources/papers/grimm-odd-2006.md`
- `sources/papers/grimm-ten-years-1999.md`
- `sources/software/algebraicabms-jl.md` — categorical (graph-rewriting) ABM in AlgebraicJulia

## Open Questions

- When is ABM scientifically preferable to equation-based modeling, and when is the additional complexity of explicit agent representation unjustified?
- How do you validate an ABM? Unlike physical models, there is no ground truth to compare against, only empirical patterns.
- Can ABM and MARL be unified into a single framework that handles both fixed-rule emergence and adaptive-rule learning?
