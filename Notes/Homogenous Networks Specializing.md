A note on terms. Network pulls a lot of different meaning. Mainly talking about actual computer networking (OSI stack, IP addresses, internet or other connections between) and abstract networks. cNetwork will be a literal, technical computer network. otherwise, its an abstract network. 

## S1: Quantification of Network 
Edges, connections between nodes, are usually drawn without a firm definition of meaning. Often its a geographic representation. Nodes area also often picked in a biased way without real definition. If I drew a computer network, it would be individual IPs and networked connections, which is fairly concrete given the highly technical nature of how they have to work. If I were drawing a network of computation with data centers, edge nodes, and users, a traditional cNetwork wouldn't make sense, but would be an intuitive bias to start with, since we're modeling computation, not the cNetwork. Cases that make this clearly ridiculous would be colocation sites, a single data center that is actually a conglomerate of many data centers at one place, or a cloud center where flex compute is used. We don't care about the location or cNetwork infrastructure, we need to focus on the computational network.

Data rate may be best if we use only one edge concept in a computer network. What matters is the size of the pipe between units. A node is harder to quantify under one metric. Computing equipment today has many functions and different data transforms. 

If we assume all systems are characterized by: inputs (including I/O, networking, sensors, user input), on-chip movement, transform rate, egress, we can talk about useful data transformed. So any node would have to be a system with a complete accounting of data input, including on-site data bases and networked connections, on-chip movement, transform rate, and output.

**Definition**
So we define a capacity boundary. A node is any region where internal movement / transform capacity is higher than the edges crossing its boundary. A boundary is where capacity drops or latency jumps. 

Each edge e has:
- Bandwidth (Be, bits/s)
- energy per bit Ee (J/bit), optional
- latency Le (s)
Granularity is the threshold p>1 where if an internal connection is at least p times faster than the best external connection, it is one node
Smaller p will split into finer sub-nodes

Each node, N, has three measures 
- I/O ceiling, Bio(N) = aggregate ingress / egress capacity at boundary
- Mem / Movement Ceiling: Bmem(N) = on-node movement (caches, DRAM, HBM, fabric)
- Transform ceiling: Bxfm(N,w) = Rops(N) / I(w)
	- Rops is nodes sustained operations / s and I (w) is operational intensity of workload w. ops -> bits/s via I(w) lets capacity live in same units as bandwidth
For a given workload w, the node's effective throughput is:
	- Teff(N,w) = min(Bio, Bmem, Bxfm(w))

## S2: Quantification of Workloads and Archetypes
To simplify and abstract our tasks, we need to generalize workload. 

w = (I, W, P, x, C, LSLO, prec)
- I : (ops/byte)
- W: (bytes)
- P: usable parallelism
- x: state fullness / resuse factor
- C: communication pattern
- LSLO: latency / tail constraint
- prec: numerical precision tolerance

Thus, Teff(N, w) = min(Bio, Bmem(W,x), Bxfm(I,prec))

**Some archetypes:**
Archetype,I_ops_per_byte,Working_Set,Parallelism_P,Reuse_χ,Comm_Pattern,Latency_SLO,Precision,Usual_Bottleneck
*Dense Compute* (DC),60.0,HBM-scale,High,Medium,Collectives (periodic all-reduce),∞ (batch),int8–fp16–fp32,HBM or fabric during collectives
*Streaming Transform* (ST),2.0,≪ LLC (pipeline),Medium–High,Low,None / linear pipeline,"Finite (e.g., 33 ms/frame)",int8–fp16–fp32,I/O or tail latency
*Memory/Scan* (MS),0.8,DRAM–HBM,High,Medium–High,Light,∞,int8–fp32,Memory bandwidth
*Irregular Graph* (IG),1.0,DRAM,Medium,Low (poor locality),PtP / shuffle,Varies,int8–fp32,Random-access memory & fabric
*Collective/Reduce* (CR),,N/A,High,N/A,Collective/shuffle dominated,∞,N/A,Interconnect / bisection bandwidth
*Online Serving* (OS),3.0,Fits in DRAM+cache tiers,High (requests),High (caches),RPC fan-out/in,p99 = 10–200 ms,int8–fp16–fp32,Tail latency bursts & I/O

*Should workload be invariant as it comes across the network or be transformed?* 
Likely transformed. Consider a workload that originates at a node. The workload then starts moving across the network, changing a lot or a little from node to node. The workload then may come back again to the origin or not. 
## S3: Global Characteristics

*Capacity and Throughput*
**Aggregate Throughput:** sum of effective node Teff
**Bisection bandwidth:** minimum cut capacity across network
**Throughput Distribution:** Nodes at saturation, uneven distributions?

*Latency Landscape*
**Path length distribution:** average p95, p99 across network
**Critical Path:** slowest diameters of communication
**Latency variance**: stable v bursty

*Utilization and Load Balance*
**Node utilization:** fraction of Teff used
**Edge utilization:** hotspots, underused
**Skew**: Gini coefficient of utilization across nodes / links

*Resilience & Robustness*
**Failure tolerance**: how much capacity remains if a fraction of nodes/edges fail?
**Redundancy**: number of disjoint paths between important node pairs.
**Graceful degradation**: does throughput degrade smoothly or catastrophically?

*Efficiency Metrics*
**Energy per bit (global):** total joules consumed / total useful bytes transformed.
**Cost per bit (global):** total $/hr / total throughput.
**Green efficiency frontier:** trade-off curve between energy and throughput.

*Specialization & Heterogeneity*
**Role diversity:** fraction of nodes that are compute-heavy vs capacity-heavy vs balanced.
**Emergent specialization:** do certain nodes become central hubs, caches, or bottlenecks without being designed that way?
**Fractal similarity:** do sub-networks look like the global one at different zoom levels?

*Information Flow Characteristics*
**Operational intensity distribution across the network:** where are workloads compute-bound vs memory-bound vs comm-bound?
**Flow motifs:** pipelines, feedback loops, fan-outs, many-to-one reduces.
**Information bottlenecks**: substructures where entropy is lost or compressed.

*Complexity Science Inspired*
Order parameters:
Global throughput (bits/sec)
Average utilization
Effective diameter (latency)
Phase transitions:
Below certain bandwidth → system fragmented
Above → system synchronized or saturating
Emergent patterns: load clustering, specialization, bottleneck cascades.

*Metrics*
- Aggregate Effective Throughput, T(sum)
- Utilization Distribution U
- Latency Diameter, Lp95 (end-end latency). Size in time, not space
- Resilience Reserve R, fraction of throughput retained after stress/failure
- Energy / Cost Efficiency nu
- Heterogeneity Index, H (diversity of node roles)
### S4: Node Utility and User / Exogeneous Nodes

Utility is a function of bytes transformed, bytes forwarded, capacity used, energy, latency penalties, loss/err penalties, uptime or path redundancy. We use market or policy weights on each.

Accordingly, nodes have cost models. Energy, latency, utlization. 

Demand-side / boundary conditions. 
