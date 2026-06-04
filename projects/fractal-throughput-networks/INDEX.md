---
type: project
name: "Fractal Throughput Networks"
status: developing
domain: networks
related_domains: [computation, complexity, dynamics]
---

# Fractal Throughput Networks

> A layered, throughput-constrained, workload-driven framework for modeling computing and communication networks — with the same lens applied across phones, GPUs, racks, data centers, ISPs, and (speculatively) biological information-processing systems. Built incrementally: one node → many nodes → workloads → utilities/pricing → adaptation → birth/death/merge/split.

## Why This Project

Most network and systems modeling either (a) lives at a specific abstraction (queue theory, Internet measurement, GPU benchmarks) and doesn't generalize, or (b) generalizes informally without explicit symbols and equations. This project tries to build a single tractable formalism that scales fractally — where a node and a network of nodes are the same kind of object viewed at different granularities — and where every symbol has units, a definition, and an equation.

## Documents

| Doc | What it covers |
|---|---|
| [[README]] | Project overview, why it exists, layered approach |
| [[model-summary]] | Core elements: nodes, edges, workloads, descriptors |
| [[dynamical-model]] | Minimal self-contained dynamical model (state, physics, utility, evolution) |
| [[node-evolution]] | Endogenous topology: birth, death, merge, split of nodes |
| [[network-specialization]] | When homogeneous networks specialize; capacity boundary as node definition |
| [[state-distribution]] | Combinatorial state-space explosion in multi-agent systems |
| [[math-background]] | Reading list — linear algebra, graphs, optimization, dynamics on networks |
| [[field-naming]] | What this area is *called* across disciplines — disambiguation aid |
| [[idea-dump]] | Scratch ideas; predator-prey-as-network, peer cooperative information flow |

## Connections to Vault Concepts

- [[concepts/networks/network-formalism]] — formal graph definition this project builds on
- [[concepts/complexity/adaptation]] — node specialization is an adaptation mechanism
- [[concepts/complexity/agent-based-modeling]] — the simulator is an ABM
- [[concepts/dynamics/INDEX]] — system evolution and stability analysis

## Status

Developing. Spec and conceptual model written; no simulator implemented yet.
