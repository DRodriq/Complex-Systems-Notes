---
type: concept
name: "Partition Function"
domain: statistical-mechanics
related_domains: [information, computation]
status: stub
provenance: literature
extends: []
instance_of: []
---

# Partition Function

## Orientation

The sum (or integral) of Boltzmann weights over all microstates of a system,
Z = Σ exp(−βE). The generating object of statistical mechanics: thermodynamic
quantities (free energy, internal energy, entropy, specific heat) are obtained
as derivatives of its logarithm. Cousin of the normalizing constant in any
probability distribution; variational inference in ML is, formally, partition-
function approximation.

## Core

<!-- to be developed from Sethna -->

## Connections

Log Z is the negative free energy (times β). Variational inference in ML
approximates log Z via the evidence lower bound — see [[stat-physics-of-learning]].
The partition function is also the moment-generating function of the energy
distribution.

## Sources

- [[sethna-entropy-order-parameters-2021]]
- [[mehta-ml-for-physicists-2019]]
