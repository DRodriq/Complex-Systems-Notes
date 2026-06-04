---
type: concept
name: "Temporal Networks"
domain: networks
related_domains: [dynamics, complexity]
status: stub
provenance: literature
contrasts_with: []
---

# Temporal Networks

## Orientation

Networks in which edges (or edge activations) carry timestamps, so the
structure is a sequence of interactions rather than a static graph. Paths
must be *time-respecting* — an edge at time t2 can only extend a path that
reached its endpoint at time t1 < t2. This breaks many assumptions of
static-network theory: epidemic thresholds, synchronization, and centrality
all depend on timing, not just topology. Phenomena unique to temporal
networks include burstiness, temporal motifs, and time-respecting-path
constraints.

## Core

<!-- to be developed from Holme & Saramäki -->

## Connections

Direct substrate for thinking about the cluster-genealogy DAG in streaming IE
work and IE-propagation dynamics. Extends [[community-structure]] and
[[scale-free-networks]] into time-dependent settings. Natural partner to
[[adaptive-networks]] (where topology evolves) and [[dynamical-systems-on-networks]]
(where states evolve on a fixed substrate).

## Sources

- [[holme-saramaki-temporal-networks-2012]]
