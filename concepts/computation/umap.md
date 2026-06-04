---
type: concept
name: "UMAP"
domain: computation
related_domains: [dynamics, information]
status: stub
provenance: mixed
extends: []
instance_of: []
precedes: []
contrasts_with: []
tags: [UMAP, dimensionality-reduction, manifold-learning, Riemannian-geometry, embeddings, topology]
---

# UMAP

> Uniform Manifold Approximation and Projection (McInnes et al., 2018): a dimensionality reduction algorithm grounded in Riemannian geometry and algebraic topology. UMAP approximates the manifold structure of high-dimensional data by constructing a weighted graph that represents the data's local geometry, then optimizing a low-dimensional representation to preserve that structure.

## Orientation

Unlike PCA (which is linear) or t-SNE (which uses a heuristic Gaussian kernel), UMAP has a rigorous mathematical foundation: it approximates the Riemannian metric of the data manifold using local fuzzy simplicial complexes, then finds a low-dimensional embedding that minimizes the cross-entropy between the high- and low-dimensional topological representations. In practice this means UMAP preserves both local neighborhood structure and global topology more faithfully than t-SNE, while being faster and more scalable. The key insight is that UMAP is not doing Euclidean nearest-neighbor search in ambient space — it is approximating geodesic distances on the data manifold.

## Connections

**Manifold hypothesis** (`concepts/dynamics/manifold-hypothesis.md`) — UMAP's entire operation assumes the manifold hypothesis; the algorithm is a practical implementation of Riemannian manifold approximation.

**Persistent homology** (`concepts/dynamics/persistent-homology.md`) — both are grounded in algebraic topology; UMAP uses fuzzy simplicial sets rather than persistent homology, but the theoretical family is the same.

**Neural networks** (`concepts/computation/neural-networks.md`) — UMAP is widely used to visualize the representation geometry of neural network layers; the manifold structure it reveals reflects the model's learned features.

## Sources

- McInnes, L., Healy, J., & Melville, J. "UMAP: Uniform Manifold Approximation and Projection for Dimension Reduction." *arXiv:1802.03426*, 2018. — The original paper; unusually readable for an algorithm paper; the mathematical sections lay out the Riemannian geometry foundation explicitly.
- McInnes, L. "How UMAP Works." UMAP documentation, https://umap-learn.readthedocs.io/en/latest/how_umap_works.html. — Accessible walkthrough of the algorithm's mathematical foundations; best first read before the paper.
