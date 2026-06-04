---
type: concept
domain: computation
related_domains: [complexity]
provenance: mixed
status: developing
relates_to:
  - target: reinforcement-learning
    relation: extends
  - target: concepts/complexity/complex-adaptive-systems
    relation: instance-of
  - target: concepts/complexity/adaptation
    relation: instance-of
  - target: concepts/complexity/agent-based-modeling
    relation: overlaps
tags: [MARL, multi-agent, co-evolution, emergent-strategies, game-theory]
---

# Multi-Agent Reinforcement Learning

> Multiple RL agents learning simultaneously in a shared environment, where each agent's learning changes the effective environment for all others — the computational instantiation of the co-evolutionary dynamics at the heart of CAS theory.

## Orientation

Multi-agent RL (MARL) is where RL becomes complex adaptive systems. In single-agent RL, the environment is stationary — the agent learns against a fixed world. In MARL, the environment includes other learning agents, making it non-stationary from each agent's perspective: as agents update their policies, the rewards and transitions change for everyone else. This is precisely the co-evolutionary dynamic that Holland identified as the defining feature of CAS.

## Core

### The Non-Stationarity Problem

The central challenge of MARL is non-stationarity. Standard RL convergence guarantees assume a stationary Markov decision process. When other agents are learning, the effective transition and reward functions change continuously — the ground is always shifting.

This has formal consequences: Q-learning does not converge in general MARL settings. More recent algorithms (MADDPG, MAPPO, QMIX) handle this by centralizing training while decentralizing execution — agents share information during learning but act independently at test time.

### Cooperation and Competition

MARL environments span a spectrum from fully cooperative (all agents share the same reward) to fully competitive (zero-sum: one agent's gain is another's loss) to mixed (most real settings: cooperation within groups, competition between them).

**Fully cooperative MARL** — the goal is to find a joint policy that maximizes team reward. Problems: credit assignment (which agent's actions contributed to the team reward?), coordination (agents must agree on a convention without explicit communication). Solutions: centralized critics, communication protocols, reward shaping.

**Fully competitive MARL** — equivalent to game theory; finding Nash equilibria. Rock-paper-scissors is the trivial case. More interesting: poker (imperfect information), Go (perfect information), auction design. AlphaGo/AlphaZero are examples of self-play in competitive MARL.

**Mixed cooperative-competitive** — teams compete against each other; within-team cooperation, between-team competition. Most real strategic settings (economics, ecology, military).

### Emergent Behavior

MARL is a natural laboratory for studying emergent social behavior — cooperation, communication, specialization, arms races, deception — arising without explicit programming. Notable examples from recent research:

- Agents developing compositional communication protocols to solve cooperative tasks (emergent language)
- Hide-and-seek agents discovering tool use, lever mechanics, and multi-step strategies not anticipated by designers (OpenAI hide-and-seek)
- Competitive agents developing escalating strategies (arms races) in simulated environments

These are emergence in the complexity science sense: collective behaviors arising from agent interactions that were not designed and could not be predicted from individual rules.

### Connection to CAS

MARL is the most explicit computational model of CAS dynamics. Holland's agents with schemas, adapting in each other's presence, with fitness determined by relative performance — this is MARL. The differences are implementation details: MARL agents use gradient-based policy updates rather than genetic algorithm rule updates, and the environment is typically simpler than a full CAS simulation. But the logical structure is identical.

## Connections

**Reinforcement learning** (`concepts/computation/reinforcement-learning.md`) — single-agent RL is the foundation; MARL extends it to interacting populations.

**Complex adaptive systems** (`concepts/complexity/complex-adaptive-systems.md`) — MARL is CAS theory in computational form; the co-evolutionary dynamic is the same.

**Agent-based modeling** (`concepts/complexity/agent-based-modeling.md`) — MARL agents are ABM agents with learning; the distinction is whether agent behavior is fixed (ABM) or adaptive (MARL).

**Adaptation thread** (`synthesis/adaptation-thread.md`) — MARL is the contemporary endpoint of the adaptation thread in computational form.

## Sources

- `sources/books/albrecht-christianos-shafer-marl-2024.md`

## Open Questions

- Do MARL systems produce co-evolutionary dynamics that match empirical predictions from evolutionary ecology (Red Queen, arms races, punctuated equilibrium)?
- What are the conditions for cooperative norms to emerge in MARL without explicit cooperative reward shaping?
- Can MARL systems serve as scientific models of real economic or social dynamics, or are the abstractions too severe?
