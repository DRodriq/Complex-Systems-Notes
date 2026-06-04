**minimal, self-contained dynamical model** you can run conceptually (or code up) to watch nodes specialize, prices settle, and global stats emerge.

# 0) State (at epoch ttt)

- **Topology:** graph G=(V,E)G=(V,E)G=(V,E)
    
- **Node ceilings:** Bioi,Bmemi,Ropsi,CiB_{io}^i, B_{mem}^i, R_{ops}^i, C^iBioi​,Bmemi​,Ropsi​,Ci
    
- **Convex costs:** Capki(Δ)=akiΔ+bkiΔ2\text{Cap}_k^i(\Delta)=a_k^i\Delta+b_k^i\Delta^2Capki​(Δ)=aki​Δ+bki​Δ2 for k∈{io,mem,ops,cap}k\in\{\text{io,mem,ops,cap}\}k∈{io,mem,ops,cap}
    
- **Policies/strategy params (learned):** θi\theta_iθi​ (routing weight, batch size, cache policy, compression level, admission)
    
- **Prices:** service prices pxfm,pbit,pstorep_{\text{xfm}},p_{\text{bit}},p_{\text{store}}pxfm​,pbit​,pstore​; link congestion λe≥0\lambda_e\ge0λe​≥0
    
- **Demand:** user arrivals r∼λU(t)r\sim \lambda_U(t)r∼λU​(t) with workload tuple w=(I,W,P,χ,C,LSLO,prec)w=(I,W,P,\chi,\mathcal{C},L_{SLO},\text{prec})w=(I,W,P,χ,C,LSLO​,prec)
    

# 1) Physics per node (unchanged)

For each node iii and workload www:

Teffi(w)=min⁡ ⁣(Bioi,  Bmemi,  Ropsi/I(w))T_{\text{eff}}^i(w)=\min\!\big(B_{io}^i,\;B_{mem}^i,\;R_{ops}^i/I(w)\big)Teffi​(w)=min(Bioi​,Bmemi​,Ropsi​/I(w))

# 2) Utility per node (for learning)

Ui=αTxfm,i+βTfwd,i+γCserved,i−δEi−ε$i−ζΦlat,i−ηΦloss,i+κRiU_i = \alpha T_{\text{xfm},i}+\beta T_{\text{fwd},i}+\gamma C_{\text{served},i} - \delta E_i-\varepsilon \$ _i-\zeta \Phi_{\text{lat},i}-\eta \Phi_{\text{loss},i}+\kappa R_iUi​=αTxfm,i​+βTfwd,i​+γCserved,i​−δEi​−ε$i​−ζΦlat,i​−ηΦloss,i​+κRi​

(Optional backbone bonus: Ui←(1+ρ flow-centralityi) UiU_i \leftarrow (1+\rho\,\text{flow-centrality}_i)\,U_iUi​←(1+ρflow-centralityi​)Ui​.)

---

# 3) One epoch (t→t+1t\rightarrow t+1t→t+1)

**(A) Route/admit workloads (given current θ,λ\theta,\lambdaθ,λ)**

- Edge **generalized cost**: ce=de+λec_e = d_e + \lambda_ece​=de​+λe​ (prop delay ded_ede​ + congestion price).
    
- For each request, pick path(s) by shortest cec_ece​ (or softmin/ECMP); admit by SLO & local policy.
    
- Apply node policies (batching, compression, caching) → this changes effective I,WI,WI,W locally.
    
- Measure realized: Txfm,i,Tfwd,i,Ei,Φlat,i,Φloss,iT_{\text{xfm},i},T_{\text{fwd},i},E_i,\Phi_{\text{lat},i},\Phi_{\text{loss},i}Txfm,i​,Tfwd,i​,Ei​,Φlat,i​,Φloss,i​.
    

**(B) Payoffs & prices**

- Node revenue: pxfmTxfm,i+pbitTfwd,i+pstoreCserved,ip_{\text{xfm}}T_{\text{xfm},i}+p_{\text{bit}}T_{\text{fwd},i}+p_{\text{store}}C_{\text{served},i}pxfm​Txfm,i​+pbit​Tfwd,i​+pstore​Cserved,i​.
    
- Link dual update (projected subgradient / dual ascent):
    

λe←[λe+ηλ (flowe−cape)]+\lambda_e \leftarrow \big[\lambda_e + \eta_\lambda\,(\text{flow}_e - \text{cap}_e)\big]_+λe​←[λe​+ηλ​(flowe​−cape​)]+​

- Optional **service price tâtonnement** (clear excess demand):
    

px←px+ηp (demandx−supplyx),x∈{xfm,bit,store}p_x \leftarrow p_x + \eta_p\,(\text{demand}_x-\text{supply}_x),\quad x\in\{\text{xfm,bit,store}\}px​←px​+ηp​(demandx​−supplyx​),x∈{xfm,bit,store}

**(C) Node policy learning (fast, CAPEX fixed)**  
Per node iii, maintain value estimates Qi(θ)Q_i(\theta)Qi​(θ). After observing UiU_iUi​:

Qi←(1−βQ)Qi+βQ UiQ_i \leftarrow (1-\beta_Q)Q_i + \beta_Q\,U_iQi​←(1−βQ​)Qi​+βQ​Ui​

Update policy (choose a few discrete actions for batching/compression/caching/admission) with **softmax**:

πi(a)∝exp⁡(Qi(a)/τ),θi∼πi\pi_i(a)\propto \exp(Q_i(a)/\tau),\quad \theta_i\sim \pi_iπi​(a)∝exp(Qi​(a)/τ),θi​∼πi​

(Anneal τ\tauτ slowly ↓ to stabilize.)

**(D) Capacity investment (slow CAPEX lane)**  
Every KKK epochs, consider small Δ\DeltaΔ per axis and accept if **net utility ↑**:

Δ⋆=arg⁡max⁡Δ∈{−ϵ,0,+ϵ}(E[Ui∣Δ]−Capki(Δ))\Delta^\star = \arg\max_{\Delta\in\{-\epsilon,0,+\epsilon\}} \Big(\mathbb{E}[U_i|\Delta]-\text{Cap}_k^i(\Delta)\Big)Δ⋆=argΔ∈{−ϵ,0,+ϵ}max​(E[Ui​∣Δ]−Capki​(Δ))

Then apply Bioi ⁣+ ⁣=Δio,  Bmemi ⁣+ ⁣=Δmem,  Ropsi ⁣+ ⁣=Δops,  Ci ⁣+ ⁣=ΔcapB_{io}^i\!+\!=\Delta_{\text{io}},\;B_{mem}^i\!+\!=\Delta_{\text{mem}},\;R_{ops}^i\!+\!=\Delta_{\text{ops}},\;C^i\!+\!=\Delta_{\text{cap}}Bioi​+=Δio​,Bmemi​+=Δmem​,Ropsi​+=Δops​,Ci+=Δcap​.

**(E) Centrality refresh**  
Recompute flow-betweenness/eigenvector centrality on **actual successful flows**; update the multiplier in the next epoch.

**(F) Shocks (optional)**  
With small probability: fail nodes/links, spike demand, change user SLO mix; observe resilience RRR.

---

# 4) Convergence & diagnostics

Track per epoch:

- **Global order parameters:** TΣT_{\Sigma}TΣ​, utilization mean/skew, Lp95L_{p95}Lp95​, RRR, efficiency η\etaη, heterogeneity HHH; plus persistence/fan-out/pipeline depth if used.
    
- **Prices:** λe\lambda_eλe​ heatmap; pxfm,pbit,pstorep_{\text{xfm}},p_{\text{bit}},p_{\text{store}}pxfm​,pbit​,pstore​ stability.
    
- **Ecology:** role counts (movers vs transformers vs storage hubs), churn of strategies, centrality distribution.
    
- **Welfare:** SLO satisfaction, blocks/deferrals, energy/$ per completed workload.
    

**Stop** when prices and roles stabilize (small deltas), or oscillations are bounded and acceptable.

---

# 5) Default knobs (work well in practice)

- Step sizes: ηλ∈[10−3,10−2],  ηp∈[10−3,10−2]\eta_\lambda\in[10^{-3},10^{-2}],\;\eta_p\in[10^{-3},10^{-2}]ηλ​∈[10−3,10−2],ηp​∈[10−3,10−2]
    
- Learning: βQ≈0.1\beta_Q\approx 0.1βQ​≈0.1, softmax τ\tauτ anneal 0.5→0.1 over runs
    
- CAPEX cadence K∈[25,100]K\in[25,100]K∈[25,100], investment step ϵ\epsilonϵ = 2–5% of current capacity
    
- Convex costs bkb_kbk​ big enough that “everything-nodes” are suboptimal
    

---

# 6) What you’ll see

- **Specialization:** some nodes push BioB_{io}Bio​ (backbones), others RopsR_{ops}Rops​ (compute hubs), others CCC (caches/storage).
    
- **Edge compute emergence:** when λe\lambda_eλe​ rises on core links, nodes shift to compress/cache/transform near sources.
    
- **Phase shifts:** as demand mix or prices change, roles reconfigure (e.g., training surge → compute co-locates with data).
    
- **Robustness:** under failures, traffic re-routes; nodes with slack/alternates gain centrality and utility.