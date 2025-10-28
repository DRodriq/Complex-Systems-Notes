**Nodes and Underlying Space**
Let X be the underlying state space (e.g., metric or measurable space).

Nodes as bounded regions under a threshold.
Fix a quantity $$q: X \to \mathbb{R} \ and \ threshold\  \theta \in \mathbb{R}.$$
Let $\mathcal{R}$ be a family of bounded subsets of $X$.

Define the admissible node set
$$
V \;=\; \big\{ R \in \mathcal{R} \;:\; \sup\{ q(x) : x \in R \} < \theta \big\}.
$$

**Directed edges and attributes**
Let $E \subseteq V \times V$ be the set of directed edges.
Let $d_e \in \mathbb{N}$ and define edge attributes (multi-weights)

$\phi_E: E \to \mathbb{R}^{d_e}, \qquad \phi_E(i,j) = w(i,j)$

(Optional) node attributes $\phi_V: V \to \mathcal{Y}$.

**Adjacency tensors (optional)**
Stack edge attributes as a 3-tensor
$$W \in \mathbb{R}^{|V|\times |V|\times d_e}) \ with \ 
(W_{i j k} = [\phi_E(i,j)]_k).$$

**Workloads** 
Workload state space and dimension
Let $d_w \in \mathbb{N}$ denote the workload state dimension and set
$$\mathcal{S} \;=\; \mathbb{R}^{d_w}$$

**Workload Population**
Let $\mathcal{W} = \{ w_k : k \in \mathcal{K} \}$ be a (finite or countable) set of workloads.

Each workload has a time-dependent node location and internal state,

$\ell_k(t) \in V, \qquad \sigma_k(t) \in \mathcal{S}$

Initial conditions are given by $(\ell_k(0)) \ and \ (\sigma_k(0)$.

**Propagation (discrete-time skeleton)**

Propagation is specified by a transition kernel

$\mathsf{K}\big( d\sigma', j \,\big|\, \sigma, i \big)$

on $(\mathcal{S} \times V$ that may depend on local attributes, e.g.
$\phi_V(i)), \  (\phi_E(i,j)$.
For each workload $(w_k)$
$$(\sigma_k(t{+}1),\, \ell_k(t{+}1)) \;\sim\; 
\mathsf{K}\big( \cdot \,\big|\, \sigma_k(t),\, \ell_k(t) \big)$$
Deterministic propagation is the special case
$$
\sigma_k(t{+}1) \;=\; F\big(\sigma_k(t),\, \ell_k(t)\big), \qquad
\ell_k(t{+}1) \;=\; \Pi\big(\sigma_k(t),\, \ell_k(t)\big)$$
for maps 
$$(F: \mathcal{S}\times V \to \mathcal{S}) and (\Pi: \mathcal{S}\times V \to V$$

**Policy- or edge-conditioned moves (optional)**
If moves are explicitly edge-based, use a two-stage kernel:

$$e_t \in \mathcal{A}(i) := \{(i,j)\in E\}, \quad
\mathbb{P}(e_t=(i,j)\,|\,\sigma,i) = \pi\big((i,j)\,;\,\sigma,i\big)$$
then update via $$\mathsf{K}_{(i,j)}(d\sigma'\,|\,\sigma)$$ and set $$ell_k(t{+}1)=j$$

**Aggregate / flow view (optional)** 

Let $\mu_t$ be a measure on $V \times \mathcal{S}$ for the workload ensemble.
The mean-field update is

$$mu_{t+1}(j, B) \;=\; \sum_{i\in V} \int_{\mathcal{S}} 
\mu_t(i, d\sigma) \int_{\mathcal{S}} \mathbf{1}_B(\sigma')\,
\mathsf{K}\big(d\sigma', j \,\big|\, \sigma, i\big)$$

**Edge flows (fluid limit)**
Alternatively, define a workload flux $f_t: E \to \mathbb{R}_{\ge 0}^{r}$ (single or multi-commodity \(r\)),
with node balance
$$
\sum_{j:(j,i)\in E} f_t(j,i) \;-\; \sum_{j:(i,j)\in E} f_t(i,j) \;=\; b_i(t)$$
and admissibility constraints tied to attributes (e.g., capacities) via $$\phi_E(i,j)$$
**Node thresholds during operation** 

Let a node load functional $L_i(t)$ (queue length, mass, energy) be derived from $mu_t$ or $f_t$.
The operating constraint is
$$
L_i(t) \;<\; \theta_i
$$
with $\theta_i$ possibly taken from $\phi_V(i)$ or inherited from the defining threshold on $q$.

**Model tuple (summary)** 
The workload-augmented network is the tuple
$$
\mathcal{G} \;=\; 
\big( X,\, V,\, E,\, \phi_V,\, \phi_E,\, \mathcal{S}(d_w),\, \mathcal{W},\, \mathsf{K}\big)
$$
(with optional flow view $f_t$, capacities, and policies $\pi$.