# Core Elements of the Framework

## 1. **Nodes**
- **Definition:** a bounded region where internal movement/transform >> external link capacity.
- **Descriptors:**
    - $B_{io}$​: ingress/egress throughput
    - $B_{mem}$: internal memory/movement throughput
    - $R_{ops}$​: sustained operations/s
    - C: capacity (bytes stored)
    - Energy, cost, latency/jitter tolerance
- **Granularity knob (ρ\rhoρ):** lets you zoom in/out fractally to define sub-nodes or super-nodes.
- **Specialization:** nodes can expand I/O, memory, compute, or storage, but each has convex cost → different roles emerge.
---

## 2. **Edges**
- **Definition:** connections where throughput/latency is lower (or costlier) than inside the nodes
- **Descriptors:**
    - Bandwidth capacity
    - Latency (mean + tail)
    - Loss probability
    - Energy per bit, cost per bit
        
- **Composition rules:**
    - Series = min throughput
    - Parallel = sum throughput
    - Latency accumulates; loss compounds

---

## 3. **Workloads**
- **Definition:** tokens that move through and/or transform within nodes.
- **Descriptor tuple:**
    $w$ = ($I$, $W$, $P$, $\chi$, $\mathcal{C}, L_{SLO}$, $\text{prec})$
    - $I$: ops/byte (operational intensity)
    - $W$: working set size
    - $P$: parallelism potential
    - $\chi$: cacheability/reuse
    - $\mathcal{C}$: communication pattern (none, ptp, shuffle, collective)
    - $L_{SLO}$​: latency constraint
    - $prec$: numerical precision required
        
- **Archetypes:** six canonical classes (Dense Compute, Streaming Transform, Memory/Scan, Irregular Graph, Collective/Reduce, Online Serving).
- **Lifecycle:** request–response, one-way storage, dissemination, pipeline, staging. Workload descriptors can transform at compute nodes, pass unchanged at movement nodes.
    

---

## 4. **Global Characteristics (Order Parameters)**
- TΣT_{\Sigma}TΣ​: aggregate effective throughput
- UUU: utilization distribution (mean, skew)
- Lp95L_{p95}Lp95​: latency diameter
- RRR: resilience reserve (performance under failures)
- η\etaη: efficiency (bytes/s per watt/$)
- HHH: heterogeneity index (role diversity)
- **Extended ones for non-returning workloads:** persistence fraction, fan-out ratio, pipeline depth, residency time
    

---

## 5. **Utility Function**
- Each node has a **goal** expressed as utility:
    U=α Txfm+β Tfwd+γ Cserved−δE−ε$−ζΦlat−ηΦloss+κRU = \alpha\,T_{\text{xfm}} + \beta\,T_{\text{fwd}} + \gamma\,C_{\text{served}} - \delta E - \varepsilon \$ - \zeta \Phi_{lat} - \eta \Phi_{loss} + \kappa RU=αTxfm​+βTfwd​+γCserved​−δE−ε$−ζΦlat​−ηΦloss​+κR
- Weights α,β,γ...\alpha,\beta,\gamma...α,β,γ... reflect environment (ISP, GPU, storage).
- **Centrality multiplier** rewards nodes that become backbones/hubs in actual flow.
    

---

## 6. **Cost Model**
- **Convex costs** for expanding node ceilings (I/O, memory, compute, capacity).
- **Energy and latency trade-offs** baked in (e.g., faster I/O → more watts, deeper pipelines → longer latency).
- Prevents “everything nodes” and drives specialization.

---

## 7. **Exogenous User Demand**
- Users = **sources/sinks** of workloads, not competitors.
- **Descriptor:**
    - Arrival process (rate, burstiness)
    - Workload mix (W\mathcal{W}W)
    - SLO/QoS requirements
    - Budget/willingness-to-pay
    - Privacy/locality constraints
- Influence network indirectly by shaping load, SLO mixes, and therefore prices and bottlenecks.
    

---

# Optional Extensions
- **Learning/Adaptation Dynamics:** how nodes update strategies (greedy, reinforcement, evolutionary).
- **Market Mechanism:** explicit pricing (pxfm_{xfm}xfm​, pbit_{bit}bit​, pstore_{store}store​) and congestion multipliers.
- **Governance/Policy Layer:** fairness, priority classes, rate limiting.
- **Stochastic Events:** failure shocks, traffic surges, demand shifts.

---

 **So far you have all the essential ingredients**:
- Nodes, edges, workloads (the physics).
- Global order parameters (the thermodynamics).
- Node utilities and costs (the economics).
- User demand (the boundary conditions).

What you _don’t yet have_ is the **dynamics**: how nodes actually _adapt over time_ under demand and costs. That’s the piece that would let you simulate emergent specialization, backbones, and strategy evolution.

| Symbol                       | Meaning                                      |    Units | Layer introduced |
| ---------------------------- | -------------------------------------------- | -------: | ---------------- |
| Δt\Delta t                   | Simulation time step                         |        s | 0                |
| BioB_{\text{io}}             | Node ingress/egress ceiling                  |  bytes/s | 0                |
| BmemB_{\text{mem}}           | Node internal movement ceiling               |  bytes/s | 0                |
| RopsR_{\text{ops}}           | Node compute rate                            |    ops/s | 0                |
| I(w)I(w)                     | Operational intensity of workload class ww   | ops/byte | 2                |
| Bxfm(N,w)B_{\text{xfm}}(N,w) | Transform ceiling at node NN for class ww    |  bytes/s | 2                |
| Teff(N,w)T_{\text{eff}}(N,w) | Effective throughput at node NN for class ww |  bytes/s | 2                |
| E[S]E[S]                     | Mean job size for class ww                   |    bytes | 0                |
| λ\lambda                     | Arrival rate (class-level)                   |   jobs/s | 0                |
| μ\mu                         | Service rate (class-level)                   |   jobs/s | 0                |
| ρ\rho                        | Utilization =λ/μ=\lambda/\mu                 |        — | 0                |
| L,WL, W                      | Mean jobs-in-system; mean response time      |  jobs, s | 0                |
| BlinkB_{\text{link}}         | Edge bandwidth                               |  bytes/s | 1                |
| LlinkL_{\text{link}}         | Edge propagation latency                     |        s | 1                |
| plossp_{\text{loss}}         | Edge loss probability                        |    [0,1] | 1                |
