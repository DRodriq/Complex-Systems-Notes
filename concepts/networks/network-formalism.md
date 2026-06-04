---
type: concept
name: "Network Formalism"
domain: networks
related_domains: [computation, dynamics, complexity]
status: developing
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Network Formalism

> Formal definitions of networks as graph-theoretic objects: from the textbook weighted directed graph $G=(V,E,w)$ through threshold-bounded node sets, multi-weight edge attributes, and workload-augmented graphs that carry state across nodes.

## Orientation

A "network" in complexity science is rarely just an unadorned graph — it carries attributes, weights, dynamics, and (often) workloads or signals moving through it. This note collects the formal definitions, from the simplest weighted directed graph up to the workload-augmented formalism used in the [[projects/fractal-throughput-networks/INDEX|Fractal Throughput Networks]] project.

## Core

### Simple weighted directed graph

The standard textbook object: $G = (V, E, w)$, where

- $V = \{1, 2, \dots, n\}$ is the finite set of vertices (nodes)
- $E \subseteq V \times V$ is the set of directed edges
- $w : E \to \mathbb{R}_{\geq 0}$ is a weight function assigning a nonnegative real to each edge

The weighted adjacency matrix is $W = (w_{ij})$ with $w_{ij} = w(i,j)$ if $(i,j) \in E$, else $0$.

Degree notions for each $i \in V$:
- Out-degree: $k_i^{\text{out}} = \sum_j w_{ij}$
- In-degree: $k_i^{\text{in}} = \sum_j w_{ji}$
- Symmetric undirected case: $k_i = k_i^{\text{out}} = k_i^{\text{in}}$

### Threshold-bounded node sets

For richer models, nodes can be defined as **bounded regions of an underlying state space under a threshold**. Let $X$ be the underlying state space (e.g., metric or measurable). Fix a quantity $q: X \to \mathbb{R}$ and threshold $\theta \in \mathbb{R}$. Let $\mathcal{R}$ be a family of bounded subsets of $X$. Define the admissible node set:

$$
V = \big\{ R \in \mathcal{R} \;:\; \sup\{ q(x) : x \in R \} < \theta \big\}
$$

This is the construction that lets you define nodes by capacity boundaries (where internal throughput exceeds boundary-crossing throughput) rather than ad hoc.

### Multi-weight edges and adjacency tensors

For edges carrying more than a single scalar, let $d_e \in \mathbb{N}$ and define edge attributes (multi-weights):

$$
\phi_E: E \to \mathbb{R}^{d_e}, \qquad \phi_E(i,j) = w(i,j)
$$

Optionally, node attributes $\phi_V: V \to \mathcal{Y}$. Stack edge attributes as a 3-tensor:

$$
W \in \mathbb{R}^{|V| \times |V| \times d_e}, \quad W_{ijk} = [\phi_E(i,j)]_k
$$

### Workload-augmented graph

To track signals or workloads moving through the network, augment the graph with a workload state space and a transition kernel.

**Workload state space:** $\mathcal{S} = \mathbb{R}^{d_w}$ for workload state dimension $d_w$.

**Workload population:** $\mathcal{W} = \{w_k : k \in \mathcal{K}\}$. Each workload has time-dependent location and internal state: $\ell_k(t) \in V$, $\sigma_k(t) \in \mathcal{S}$.

**Discrete-time propagation:** transition kernel
$$
\mathsf{K}\big(d\sigma', j \,\big|\, \sigma, i\big)
$$
on $\mathcal{S} \times V$ (may depend on local attributes $\phi_V(i), \phi_E(i,j)$). Update:
$$
(\sigma_k(t{+}1), \ell_k(t{+}1)) \sim \mathsf{K}\big(\cdot \,\big|\, \sigma_k(t), \ell_k(t)\big)
$$

Deterministic case:
$$
\sigma_k(t{+}1) = F(\sigma_k(t), \ell_k(t)), \qquad \ell_k(t{+}1) = \Pi(\sigma_k(t), \ell_k(t))
$$
for maps $F: \mathcal{S} \times V \to \mathcal{S}$ and $\Pi: \mathcal{S} \times V \to V$.

**Aggregate / flow view:** for an ensemble measure $\mu_t$ on $V \times \mathcal{S}$, the mean-field update is
$$
\mu_{t+1}(j, B) = \sum_{i \in V} \int_{\mathcal{S}} \mu_t(i, d\sigma) \int_{\mathcal{S}} \mathbf{1}_B(\sigma') \, \mathsf{K}(d\sigma', j \,|\, \sigma, i)
$$

**Edge flows (fluid limit):** workload flux $f_t: E \to \mathbb{R}_{\geq 0}^r$ with node balance:
$$
\sum_{j : (j,i) \in E} f_t(j,i) - \sum_{j : (i,j) \in E} f_t(i,j) = b_i(t)
$$

**Operating constraint:** node load functional $L_i(t)$ (queue length, mass, energy) derived from $\mu_t$ or $f_t$ satisfies $L_i(t) < \theta_i$, with $\theta_i$ possibly inherited from the defining threshold on $q$.

**Model tuple:**
$$
\mathcal{G} = (X, V, E, \phi_V, \phi_E, \mathcal{S}(d_w), \mathcal{W}, \mathsf{K})
$$

with optional flow view $f_t$, capacities, and routing policies $\pi$.

## Connections

- The threshold-bounded node construction enables [[projects/fractal-throughput-networks/INDEX|fractal throughput networks]], where capacity boundaries define what counts as a node at a chosen granularity.
- [[dynamical-systems-on-networks]] uses this formalism as the substrate for state evolution.
- [[temporal-networks]] extends $E$ to time-varying edge sets $E(t)$.
- [[adaptive-networks]] allow $V$ and $E$ themselves to evolve.

## Sources

(stub — primary references in [[sources/books/newman-networks-2018]] and [[sources/books/barabasi-network-science-2016]])
