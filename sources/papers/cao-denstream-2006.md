---
type: source-paper
title: "Density-Based Clustering over an Evolving Data Stream with Noise"
author: [cao-feng, ester-martin, qian-weining, zhou-aoying]
year: 2006
status: read
domain: computation
related_domains: [dynamics, information]
key_concepts: [streaming-clustering, density-based-clustering, micro-clusters, incremental-learning, data-streams, noise-handling]
published_in: siam-sdm-2006
---

# Density-Based Clustering over an Evolving Data Stream with Noise — Cao, Ester, Qian, Zhou (2006)

> The paper that introduced DenStream: a density-based streaming clustering algorithm that maintains micro-cluster summaries (CF vectors with exponential decay) to support arbitrary-shape cluster discovery in evolving streams without requiring the cluster count to be pre-specified and without noise contaminating the cluster structure.

## Key Contribution

DenStream solves the gap left by CluStream (Aggarwal et al., 2003) — the dominant prior method — which required a pre-specified fixed number of micro-clusters and produced only spherical clusters via k-means. DenStream instead maintains a two-tier structure: **p-micro-clusters** (potential clusters, weight ≥ βµ) and **o-micro-clusters** (outlier candidates, weight < βµ) in a separate outlier-buffer. Points decay exponentially with time (f(t) = 2^{−λt}), so old evidence fades. Promotion from outlier to potential cluster happens automatically when an o-micro-cluster accumulates enough weighted density. A variant of DBSCAN is applied to the p-micro-cluster set on demand to generate final clusters.

**Original application context:** network monitoring (TCP connection intrusion detection), environmental sensor streams (pressure/temperature/humidity), web click streams. Validated on KDD CUP'99 Network Intrusion and KDD CUP'98 Charitable Donation datasets.

## Vault Relevance

The foundational reference for any streaming density-based clustering architecture. Directly relevant to pipeline designs that need incremental waypoint declaration (stable centroids) without full corpus reprocessing. The decay parameter λ and the p/o-micro-cluster promotion mechanism are the key design primitives. See also: `concepts/dynamics/manifold-hypothesis.md`, `concepts/computation/umap.md`.

## Full Reference

Cao, F., Ester, M., Qian, W., & Zhou, A. "Density-Based Clustering over an Evolving Data Stream with Noise." In *Proceedings of the 2006 SIAM International Conference on Data Mining (SDM)*, pp. 328–339. SIAM, 2006.

PDF: https://www.cs.sfu.ca/~ester/papers/SDM2006.DenStream.final.pdf
