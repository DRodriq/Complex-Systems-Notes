---
type: source-index
domain: category-theory
related_domains: [computation, complexity]
status: developing
---

# Software & Tools

> Software packages that *implement* the theory the vault tracks — annotated with maintenance status. The first cluster is the AlgebraicJulia ecosystem (the computational substrate under the [[concepts/category-theory/INDEX|category-theory]] cluster) plus its categorical-cybernetics and conventional-ABM neighbours. A software node records what a package does, what theory it realizes (`implements`), what it depends on (`builds_on`), and a `maintenance:` status — which ages, so each note dates its basis (e.g. last-commit date).

## Noded

- [[sources/software/algebraicabms-jl]] — stochastic graph rewriting for ABMs; realizes [[sources/papers/brown-categorical-rewriting-2023]]. *Research-grade* (last activity ~Aug 2025; no releases; unstable API).

## Backlog — AlgebraicJulia ecosystem (not yet noded)

Maintenance status as of June 2026, to be verified per-node when each is written.

| Package | What it is | Maintenance |
|---|---|---|
| `Catlab.jl` | Core ACT library — categories, acsets, wiring diagrams | Active, central |
| `ACSets.jl` | The attributed C-set data structure | Active |
| `GATlab.jl` | Generalized algebraic theories backing Catlab | Active |
| `AlgebraicRewriting.jl` | DPO/SPO/SqPO rewriting for C-sets — the engine under AlgebraicABMs | Active |
| `AlgebraicDynamics.jl` | Compose open dynamical systems via operads (continuous & discrete) | Maintained |
| `AlgebraicPetri.jl` | Open Petri nets; typed stratification | Maintained |
| `Decapodes.jl` (+ `CombinatorialSpaces.jl`, `DiagrammaticEquations.jl`) | DEC-based diagrammatic multiphysics PDEs | Active |
| `Semagrams.jl` | Graphical editors for wiring diagrams / Petri nets | Intermittent |

## Backlog — Topos Institute / adjacent

| Tool | What it is | Maintenance |
|---|---|---|
| **CatColab** (ToposInstitute/CatColab) | Web-based collaborative categorical modelling environment; possible successor interface | Actively developed (2024–) |
| `open-games-engine` (20squares / Hedges / Zahn) | Compositional games with learning agents, in Haskell | Maintained |

## Backlog — conventional ABM baselines (non-categorical, for contrast)

| Tool | What it is | Maintenance |
|---|---|---|
| `Agents.jl` (Julia) | Mature, fast, well-documented ABM framework — the pragmatic non-ACT option | Active |
| NetLogo / Mesa (Python) | Classic ABM platforms | Active |

*Add a full node when a package becomes load-bearing for a concept or project; until then the row here marks the slot.*
