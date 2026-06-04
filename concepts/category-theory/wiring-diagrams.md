---
type: concept
name: "Wiring Diagrams"
domain: category-theory
related_domains: [computation, dynamics]
status: stub
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Wiring Diagrams

> Boxes-with-ports connected by wires — a syntax for how systems-in-boxes can be plugged together. Formally an **operad** (Spivak 2013); concrete systems are then **algebras over that operad**, with composition of diagrams reflected by composition of systems. The substrate underneath both **undirected wiring diagrams** (used for symmetric composition, à la open Petri nets) and **directed wiring diagrams** (used for input/output processes).

## Orientation

Wiring diagrams formalize the engineer's intuition that complex systems are built by drawing boxes and connecting them with wires. [[david-spivak|Spivak]]'s 2013 paper (produced during his MIT period, before the founding of the [[institutions/topos-institute|Topos Institute]]) made this precise: wiring diagrams (of various flavours — undirected, directed, with traces) form **operads**, and assigning a concrete system to each box and the composite system to each diagram is an **algebra** over that operad. The flexibility of "what counts as a system" is huge — dynamical systems, databases, processes, relations all support such algebras — which is why the construction recurs across applied category theory.

### As composition in monoidal categories

Wiring diagrams are also the diagrammatic calculus of **symmetric monoidal categories**: each box is a morphism, parallel composition is the monoidal product ⊗, and serial composition is ordinary composition of morphisms. Reading "wiring diagram" as "string diagram in a symmetric monoidal category" is the more general framing; Spivak's operadic treatment then specializes this for the use cases (open systems, databases, dynamical systems) where the algebra over the wiring-diagram operad is the construction of interest.

### MIT → Topos lineage

The wiring-diagram-as-operad line is one of the threads carried from Spivak's MIT period into the [[institutions/topos-institute|Topos Institute]] from 2020 onward, where it became the syntactic substrate for the AlgebraicJulia software stack ([[evan-patterson|Patterson]], [[james-fairbanks|Fairbanks]], and collaborators). The pipeline from "wiring diagrams as a categorical object" to "wiring diagrams as a working software data structure" runs through [[sources/papers/spivak-operad-wiring-diagrams-2013|Spivak 2013]] → [[sources/papers/vagner-spivak-lerman-open-dynamical-2015|Vagner–Spivak–Lerman 2015]] → [[sources/papers/patterson-categorical-data-structures-2022|Patterson–Lynch–Fairbanks 2022]] (Catlab/ACSets) → [[sources/papers/libkind-baas-patterson-fairbanks-operadic-dynamical-2021|Libkind et al. 2021]] (operadic dynamical-systems modelling in code).

## Core

(stub — to be filled when this node develops)

## Connections

- The syntactic side of [[open-systems]] composition. Open systems supply the algebra; wiring diagrams supply the operad.
- Used by [[sources/papers/vagner-spivak-lerman-open-dynamical-2015]] to compose arbitrary open dynamical systems — the categorical basis of AlgebraicDynamics.jl.
- A central tool in [[categorical-systems-theory]] and in the AlgebraicJulia software stack (Catlab.jl provides wiring-diagram data structures).
- [[polynomial-functors]] extend this picture to systems with *mode-dependent* interfaces (the available wires depend on the system's current state).

## Sources

- [[sources/papers/spivak-operad-wiring-diagrams-2013]] — wiring diagrams as an operad.
- [[sources/papers/vagner-spivak-lerman-open-dynamical-2015]] — algebras of open dynamical systems on the operad of wiring diagrams.
- [[sources/papers/patterson-categorical-data-structures-2022]] — ACSets and Catlab.jl, the data-structure substrate that makes wiring-diagram algebras implementable.
- [[sources/papers/libkind-baas-patterson-fairbanks-operadic-dynamical-2021]] — operadic dynamical-systems modelling realized in AlgebraicJulia code.
