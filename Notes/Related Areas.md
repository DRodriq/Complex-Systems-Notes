### Symbolic Dynamics
Suppose you have a dynamical system: $T:X->X$ on some space, $X$
Trajectories are continuous: $x, T(x),T^{2} (x)...$

Symbolic dynamics discretized this by:
Partitioning X into regions $R_1, R_2,...,R_m$, and assigning a symbol (A,B,C,...) to each region
We can then replace each trajectory with the sequence of symbols visited. Thus, continuous dynamics occur as sequences over a finite alphabet.

### Markov Partitions
Adding to the above, not every partition might give you a neat symbolic model.

A Markov partition is a special partition of $X$ into bounded regions with the properties:
- If a trajectory can go from $R_i$ to $R_j$ in one step, then any point in $R_i$ can map under $T$ into $R_j$
- When transitions are well-defined and memoryless, they are Markov
	- ie; the probability of transitioning to the next state depends only on the current state
With a Markov chain, the symbolic sequence satisfied the rules of a [[Markov Chain]]:
- Allowed transitions are encoded in an adjacency matrix
- The dynamics of T are conjugate or semi-conjugate to a shift of finite type

### Computational Geometry Networks
Computational geometry asks: given a set of points or regions in $R^d$, how do we compute structures (graphs, partitions, coverings) that capture relationships?

**Delaunay Triangulation Graph:** 
- Start with points in $R^2$ or higher
- construct the triangulation where nodes = points, edges = adjacency
**Voronoi Diagram**:
- Partition space into cells: each cell = all points closer to one generator point than another
- Nodes = sites (generators), edges = adjacency of cells
- **Proximity Graphs**
    - **k-nearest neighbor graph**: each point connects to its k nearest neighbors.
    - **Gabriel graph**: edge (i,j) exists if the circle with diameter (i,j) contains no other points.
    - **Relative neighborhood graph**: edge (i,j) exists if no other point is closer to both i and j.
- **Intersection Graphs**
    - Nodes = geometric objects (disks, polygons, polytopes).
    - Edge if objects intersect or are within threshold distance.
    - Common in wireless/communication networks, computational biology.
