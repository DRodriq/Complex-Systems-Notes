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

Wiring diagrams formalize the engineer's intuition that complex systems are built by drawing boxes and connecting them with wires. Spivak's 2013 paper made this precise: wiring diagrams (of various flavours — undirected, directed, with traces) form operads, and assigning a concrete system to each box and the composite system to each diagram is an algebra over that operad. The flexibility of "what counts as a system" is huge — dynamical systems, databases, processes, relations all support such algebras — which is why the construction recurs across applied category theory.

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
- [[sources/papers/patterson-categorical-data-structures-2022]] — ACSets and Catlab, the data-structure substrate that makes wiring-diagram algebras implementable.
