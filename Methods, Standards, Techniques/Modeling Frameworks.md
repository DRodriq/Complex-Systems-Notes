- **Archaeological Simulation Protocols (Lake, 2014)**
    - Suggested workflows for rigor, transparency, replication in ABM.
    - A methodology that can be applied across [[NetLogo]]/[[Repast/etc.
- **Archaeological Simulation Toolkit (various labs, e.g., Kiel University, Santa Fe Institute)**
    - Often project-specific toolchains built on Repast/Mesa.
    - Example: **DISPERSCA** (2025) → implemented as cellular automata ABM for Iberian hunter-gatherer mobility.
- **OpenABM / CoMSES Net (Community of Modeling for Social-Ecological Systems)**
    - Repository and discussion hub for ABMs, including archaeological models.
    - Offers models + frameworks that can be adapted.
- **Paleoscape Models (African Archaeology)**
    - GIS + ABM hybrids modeling resource distribution, mobility, demography.
    - Implemented mostly in Repast or custom code.

Across these implementations, most models require you to specify:
1. **Landscape**: resource patches, water sources, barriers (imported via GIS or randomized).
2. **Agents**: forager groups/families with rules for movement, reproduction, mortality.
3. **Resource Dynamics**: renewable/depleting patches, seasonality, climate forcing.
4. **Social Rules**: cooperation, sharing, conflict, marriage exchange.
5. **Scaling**: time steps (daily, seasonal, annual) and spatial resolution.