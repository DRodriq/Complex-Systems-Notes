# Core foundations (start here)

- **Linear Algebra & Numerical Linear Algebra**  
    Strang, _Linear Algebra and Its Applications_; Trefethen & Bau, _Numerical Linear Algebra_.
    
- **Probability & Stochastic Processes (non-measure)**  
    Blitzstein & Hwang, _Introduction to Probability_; Norris, _Markov Chains_ (short, focused).
    
- **Algorithms & Data Structures**  
    Kleinberg & Tardos, _Algorithm Design_.
    

# Network science & optimization (central to your model)

- **Graph Theory / Network Science**  
    West, _Introduction to Graph Theory_ (structure); Newman, _Networks_ (applied network science).
    
- **Network Optimization & Flows** (capacities, min-cut, max-flow, routing)  
    Ahuja–Magnanti–Orlin, _Network Flows_; Bertsekas, _Network Optimization_.
    
- **Convex Optimization & Polyhedral Geometry** (nodes as polytopes)  
    Boyd & Vandenberghe, _Convex Optimization_ (free); Ziegler, _Lectures on Polytopes_ (reference).
    

# Dynamics on networks (workloads/signals moving)

- **Stochastic Models on Graphs** (random walks, diffusion, epidemics)  
    Levin–Peres–Wilmer, _Markov Chains and Mixing Times_ (free).
    
- **Queueing & Discrete-Event Simulation** (if workloads queue/wait)  
    Gross & Harris, _Fundamentals of Queueing Theory_; Law, _Simulation Modeling & Analysis_.
    

# Geometry-based networks & coarse-graining

- **Computational Geometry** (Voronoi/Delaunay, intersection graphs)  
    de Berg et al., _Computational Geometry: Algorithms and Applications_.
    
- **Dynamical Systems (applied level)**  
    Strogatz, _Nonlinear Dynamics and Chaos_.
    
- **Symbolic Dynamics / Markov Partitions** (coarse-graining continuous systems)  
    Lind & Marcus, _An Introduction to Symbolic Dynamics and Coding_ (core).
    

# Information & tensors (for multi-attribute edges, explainability)

- **Information Theory** (for “explainable” signals/flows, entropy)  
    Cover & Thomas, _Elements of Information Theory_.
    
- **Tensor basics (practical)**  
    Kolda & Bader, “Tensor Decompositions and Applications” (SIAM Review 2009).
    

# If you want the rigorous underpinnings (optional)

- **Real Analysis → Measure-theoretic Probability**  
    Abbott, _Understanding Analysis_ → Durrett, _Probability: Theory and Examples_.  
    (Only needed if you want full measure-theory formality for kernels.)
    

---

## Minimal study sequence (12–16 weeks, practical-first)

1. **Weeks 1–4:** Linear algebra refresh; probability to Markov chains; implement shortest paths & random walks.
    
2. **Weeks 5–8:** Network flows + convex optimization; code max-flow/min-cut; implement scalar→vector edge weights (adjacency tensor).
    
3. **Weeks 9–12:** Discrete-event simulation (queues) _or_ diffusion on graphs; add Explainable Transition Records (ETR) logging; basic viz.
    
4. **Stretch:** Strogatz (dynamics) + de Berg (computational geometry) _or_ Lind–Marcus (symbolic dynamics), depending on which direction you lean.
    

---

## Mapping subjects to your model pieces

- **Nodes as polytopes:** Convex optimization, polyhedral theory.
    
- **Adjacency tensor (multi-weights):** Linear/numerical algebra + tensor basics.
    
- **Workloads + kernels:** Markov chains, stochastic processes; queueing/DES if needed.
    
- **Flows/capacities:** Network optimization.
    
- **Spatial/region nodes:** Computational geometry.
    
- **Coarse-graining / partitions:** Dynamical systems + symbolic dynamics.
    
- **Transparency/metrics:** Information theory (entropy, mutual info) for interpretable summaries.
    

If you tell me which **two tracks** you want to emphasize first (e.g., “flows + queues” vs “diffusion + geometry”), I’ll turn this into a focused 8-week plan with concrete exercises and build targets.