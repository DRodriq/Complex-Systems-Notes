$G=(V,E,w)$
- $V = {1,2,\dots,n}$ is the finite set of vertices (nodes).
- $E \subseteq V \times V$ is the set of directed edges.
- $w : E \to \mathbb{R}_{\geq 0}$ is a weight function assigning a nonnegative real weight to each edge.
*Our network is the set of finite vertices, V, and the set of directed edges E. Each edge is an equation mapping to a real nonnegative number.*
---
### Adjacency representation
Define the weighted adjacency matrix

$W = (wᵢⱼ)$ with entries:

$wᵢⱼ = w(i,j)$ if $(i,j) ∈ E,$  
$wᵢⱼ = 0$ otherwise
*Our weights are stored in an adjacency matrix*

---

### Degree notions

For each $i ∈ V$:

$kᵢ^{out} = Σⱼ wᵢⱼ$ (out-degree)  
$kᵢ^{in} = Σⱼ wⱼᵢ$ (in-degree)
*The degree of a node is the sum of weights out, and weights in respectively*

---

### Neighborhoods

$N^{out(i)} = { j ∈ V : (i,j) ∈ E }$  
$N^{in(i)} = { j ∈ V : (j,i) ∈ E }$
*The neighborhood of a node is the set of nodes connected as out edges out and edges in*

---

### State Space, X
Phase space, metric space, manifold, embedding space, habitat space

X is an n-dimensional set of possible states, positions, or configurations of the system under study.

---

### Nodes
A node $i ∈ V$ is a bounded region in $X$
$R{i} ⊆ X$ : $q:X->R$ satisfies $sup \{q(x):x∈Ri​\} <θ,$
For some threshold $θ ∈ R$

Thus: $V =$ {$R{i} ⊆ X:$   $sup \{q(x):x∈Ri​\} <θ$} 
For some threshold $θ ∈ R$
*Nodes are a distinct region bounded in some value within X*

---
## Edges
An edge is an ordered pair $(R{i}, R{j})∈VxV$
Each edge is assigned a multi-dimensional weight vector via 
$ϕ{E}:VxV->R^d$ , $ϕ{E}(R{i},R{j})=(w{1},...,w{d})$

$G=(V,E,ϕV​,ϕE​)$

## Workloads or Tokens
A set of propagating objects $W=${$w_1,w_2,...$}
Each $w_k$ has:
- A source node
- a state vector of dimension
	- where $m=dim(σ)$
	- $d_w$ is dimension of workload state, usually $S=R^m$
- a propagation rule, or destination

Thus:
$w_k=(i,σ_k,π_k)$
with $σ_k ∈ R^{d_w}$


That’s the **core definition**. From here, we can expand in different directions depending on your model:
- **Node/edge attributes**: add $\phi_V : V \to \mathcal{X}$, $\phi_E : E \to \mathcal{Y}$.
- **Dynamics on the network**: define $x:V \to \mathbb{R}$ and an update rule using $W$.
- **Flows / capacities**: add $c:E \to \mathbb{R}_{>0}$ (capacity), $f:E \to \mathbb{R}_{\geq 0}$ (flow).
- **Temporal / evolving networks**: define $G_t = (V, E_t, w_t)$ for $t \in \mathcal{T}$.