# Fractal Throughput Networks — Layered Simulator & Spec (README)

A minimal, **layered** framework for modeling computing (and communication) networks as **throughput-constrained, workload-driven** systems. The goal is to build the model **slowly and modularly**—starting from the simplest queue and adding one feature at a time—while keeping every definition, symbol, and equation explicit.

---

## Why this project exists
- **Clarity first.** Every symbol has a definition, units, and an equation you can trace.
- **Layering.** Start with the absolute basics (one node, one queue), then add: networks → workload archetypes → utilities/pricing → adaptation → node birth/death/merge/split.
- **Universality.** Same lens works for phones, GPUs, racks, data centers, ISPs, and even biological information-processing by focusing on **bits moved and transformed**.

---

## Core concepts (at a glance)
- **Node**: a service center with ceilings on I/O, memory movement, and compute.
- **Edge**: a link with bandwidth, latency, and loss.
- **Workload**: a token with size and **operational intensity** III (ops/byte).
- **Effective throughput**: the bottleneck minimum across a node’s ceilings.

---

## Symbols, units, and mapping

|Symbol|Meaning|Units|Layer introduced|
|---|---|---|---|
|Δt\Delta tΔt|Simulation time step|s|0|
|BioB_{\text{io}}Bio​|Node ingress/egress ceiling|bytes/s|0|
|BmemB_{\text{mem}}Bmem​|Node internal movement ceiling|bytes/s|0|
|RopsR_{\text{ops}}Rops​|Node compute rate|ops/s|0|
|I(w)I(w)I(w)|Operational intensity of workload class www|ops/byte|2|
|Bxfm(N,w)B_{\text{xfm}}(N,w)Bxfm​(N,w)|Transform ceiling at node NNN for class www|bytes/s|2|
|Teff(N,w)T_{\text{eff}}(N,w)Teff​(N,w)|Effective throughput at node NNN for class www|bytes/s|2|
|E[S]E[S]E[S]|Mean job size for class www|bytes|0|
|λ\lambdaλ|Arrival rate (class-level)|jobs/s|0|
|μ\muμ|Service rate (class-level)|jobs/s|0|
|ρ\rhoρ|Utilization =λ/μ=\lambda/\mu=λ/μ|—|0|
|L,WL, WL,W|Mean jobs-in-system; mean response time|jobs, s|0|
|BlinkB_{\text{link}}Blink​|Edge bandwidth|bytes/s|1|
|LlinkL_{\text{link}}Llink​|Edge propagation latency|s|1|
|plossp_{\text{loss}}ploss​|Edge loss probability|[0,1]|1|

**Key equations**

- Transform ceiling (roofline-style), per node NNN and workload class www:
    Bxfm(N,w)=Rops(N)I(w)[bytes/s]B_{\text{xfm}}(N,w) = \frac{R_{\text{ops}}(N)}{I(w)} \quad\text{[bytes/s]}Bxfm​(N,w)=I(w)Rops​(N)​[bytes/s]
- Effective throughput (the bottleneck minimum):
    Teff(N,w)=min⁡ ⁣(Bio(N),  Bmem(N),  Bxfm(N,w))T_{\text{eff}}(N,w) = \min\!\big(B_{\text{io}}(N),\; B_{\text{mem}}(N),\; B_{\text{xfm}}(N,w)\big)Teff​(N,w)=min(Bio​(N),Bmem​(N),Bxfm​(N,w))
- Map bytes/s to jobs/s (Layer 0 analytic M/M/1 approximation):
    μ(N,w)=Teff(N,w)E[S]\mu(N,w) = \frac{T_{\text{eff}}(N,w)}{E[S]}μ(N,w)=E[S]Teff​(N,w)​
- M/M/1 steady state (valid when λ<μ\lambda < \muλ<μ):
    ρ=λμ,L=ρ1−ρ,W=1μ−λ\rho=\frac{\lambda}{\mu},\qquad L=\frac{\rho}{1-\rho},\qquad W=\frac{1}{\mu-\lambda}ρ=μλ​,L=1−ρρ​,W=μ−λ1​

---

## Layered roadmap

### Layer 0 — Single service center (M/M/1 baseline)
- One node, one workload class, Poisson arrivals λ\lambdaλ.
- Service bounded by TeffT_{\text{eff}}Teff​ (derived from Bio,Bmem,Rops,IB_{\text{io}}, B_{\text{mem}}, R_{\text{ops}}, IBio​,Bmem​,Rops​,I).
- Outputs: ρ,L,W\rho, L, Wρ,L,W (analytic) and a consistent discrete-time queue.

### Layer 1 — Fixed topology queueing network

- Multiple nodes and directed edges with (Blink,Llink,ploss)(B_{\text{link}}, L_{\text{link}}, p_{\text{loss}})(Blink​,Llink​,ploss​).
- Fixed routing probabilities (per class).
- Conservation: per-step served bytes ≤ TeffΔtT_{\text{eff}} \Delta tTeff​Δt; per-edge transfer ≤ BlinkΔtB_{\text{link}}\Delta tBlink​Δt.

### Layer 2 — Workload archetypes (multiple classes)

- Each class www: arrival rate λw\lambda_wλw​, mean size E[Sw]E[S_w]E[Sw​], intensity I(w)I(w)I(w).
- Processor sharing across classes (conservative); still respecting per-class Teff(N,w)T_{\text{eff}}(N,w)Teff​(N,w).
- This is enough to study **compute-bound vs memory-bound vs I/O-bound** behavior across the network.

### Layer 3 — Utilities, SLOs, and pricing (optional)

- Per-node utility (revenue from transformed/forwarded bytes and capacity served minus energy/cost/latency penalties).
- Link congestion prices; SLO tiers.

### Layer 4 — Adaptation (optional)

- Nodes adjust policies (batching, compression, admission, caching) to maximize utility.
- Simple bandit/softmax or RL over a discrete action set.

### Layer 5 — Node formation (optional)

- Birth, death, merge, split with explicit costs; preferential attachment on **useful flow**.
- Endogenous topology evolution driven by unmet demand and profitability.

> You can stop at **any layer** and still have a coherent, publishable model.

---

## Data model (configuration sketch)

All values in **SI units**: seconds, bytes, bytes/s, ops/s. Here’s a minimal JSON/YAML-style sketch:

`time:   dt: 0.1        # seconds per step   steps: 1000  nodes:   nodeA:     B_io: 5.0e9          # bytes/s     B_mem: 5.0e9         # bytes/s     R_ops: 1.0e12        # ops/s     # C (capacity) reserved for future layers     sources:       class1:         lambda: 5.0      # jobs/s  (exogenous arrivals at nodeA)     routing: {}          # per-class overrides (optional)  edges:   # - u: nodeA   #   v: nodeB   #   B_link: 1.0e9      # bytes/s   #   L_link: 0.01       # s   #   p_loss: 0.0  workloads:   class1:     I: 3.0               # ops/byte     size_bytes_mean: 1.0e6     route:       nodeA: 1.0         # probability mass over next hops (Layer 1+)`

---

## Invariants & sanity checks

- **Bottleneck bound:** served bytes per class per node per step ≤ Teff(N,w)ΔtT_{\text{eff}}(N,w)\Delta tTeff​(N,w)Δt.
- **Edge capacity:** bytes transferred per edge per step ≤ BlinkΔtB_{\text{link}}\Delta tBlink​Δt.
- **Routing probabilities:** sum to 1.0 for each class at each routing decision.
- **Stability (Layer 0 analytic):** warn when λ≥μ\lambda \ge \muλ≥μ for any class.

---

## Design principles

- **Traceability:** Every variable in code maps to a symbol and equation in the spec.
- **Small steps:** Each layer is self-consistent and testable on its own.
- **Deterministic knobs, stochastic arrivals:** The physics is fixed; arrivals make it realistic.
- **No hidden magic:** If a capacity or policy changes, it’s explicit in the config or layer logic.

---

## Validation plan

1. **Layer 0:** Compare simulated queue length/latency against M/M/1 formulas.
2. **Layer 1:** Check conservation across edges and latency accumulation with synthetic paths.
3. **Layer 2:** Sweep I(w)I(w)I(w) to reproduce roofline behavior (compute- vs memory- vs I/O-bound).
4. **Regression tests:** seed-based runs produce stable aggregate metrics within tolerance.