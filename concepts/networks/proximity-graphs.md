---
type: concept
name: "Proximity Graphs"
domain: networks
related_domains: [geometry, computation]
status: stub
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Proximity Graphs

> Network structures derived from geometric data: given a set of points or regions in $\mathbb{R}^d$, construct graphs whose edges encode spatial proximity or adjacency. The basic tool kit of computational geometry where it meets network science.

## Orientation

Many networks in physical, geographic, and sensor systems aren't given as abstract edge lists — they have to be constructed from a set of points in space. Proximity graphs and related geometric graph constructions are the standard tools for this.

## Core

### Delaunay triangulation

Start with points in $\mathbb{R}^2$ (or higher). Construct the triangulation where nodes = points, edges = adjacency in the triangulation. Equivalently: a triangulation in which the circumscribed circle of every triangle contains no other points.

### Voronoi diagram

Partition space into cells: each cell = all points closer to one generator point than to any other. Nodes = sites (generators), edges = adjacency of cells. Dual to the Delaunay triangulation.

### Proximity graphs (other variants)

- **k-nearest neighbor graph** — each point connects to its $k$ nearest neighbors.
- **Gabriel graph** — edge $(i,j)$ exists if the circle with diameter $(i,j)$ contains no other points.
- **Relative neighborhood graph** — edge $(i,j)$ exists if no other point is closer to both $i$ and $j$ than they are to each other.

### Intersection graphs

- Nodes = geometric objects (disks, polygons, polytopes).
- Edge if objects intersect or are within a threshold distance.
- Common in wireless/communication networks, computational biology.

## Connections

- Substrate for [[concepts/networks/network-formalism|network formalism]] in geometric settings.
- Related to [[concepts/geometry/INDEX|computational geometry]] tools.
- Standard construction for spatial agent networks in [[concepts/complexity/agent-based-modeling|ABM]] of physical systems.

## Sources

(stub)
