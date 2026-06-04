---
type: concept
name: "Open Systems (Categorical)"
domain: category-theory
related_domains: [dynamics, complexity]
status: stub
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Open Systems (Categorical)

> Systems with explicit boundaries, formalized so that composing them along shared boundaries yields a new system of the same kind. The standard categorical machinery: **decorated cospans** (Fong), **structured cospans** (Baez & Courser), and their application to **open Petri nets** (Baez & Master) and **open reaction networks** (Baez & Pollard).

## Orientation

The shift from closed to open systems is what makes categorical modelling of dynamical systems possible at scale: rather than describing a complete system in one shot, you describe primitive open systems with input/output "feet" and a composition rule that glues them along those feet. The mathematics for this matured in the late 2010s through Fong's thesis (decorated cospans) and Baez & Courser's structured-cospans framework, which generalized the construction and clarified its categorical properties.

## Core

(stub — to be filled when this node develops)

## Connections

- [[wiring-diagrams]] are the syntactic operad over which open systems compose; open systems are typically algebras over that operad.
- [[functorial-semantics]] is the lens: the assignment "open system → behaviour" is asked to be a functor (e.g. open reaction network → rate equation, per Baez–Pollard).
- [[generative-effects]] sit precisely at the points where that semantic functor fails to preserve joins — i.e. where the composite's behaviour is more than the sum of the parts'.
- Substrate for [[categorical-systems-theory]] (Myers' double-categorical synthesis) and for the [[polynomial-functors]] approach to interactive open systems.

## Sources

- [[sources/papers/fong-algebra-open-systems-2016]] — decorated cospans, the formal home of open systems and generative effects.
- [[sources/papers/baez-courser-structured-cospans-2020]] — generalized machinery; "structured cospans" subsumes decorated cospans for many cases.
- [[sources/papers/baez-master-open-petri-nets-2020]] — categorical foundation for open Petri nets.
- [[sources/papers/baez-pollard-reaction-networks-2017]] — open reaction networks; the rate-equation assignment is functorial.
- [[sources/papers/vagner-spivak-lerman-open-dynamical-2015]] — open dynamical systems composed via wiring diagrams.
