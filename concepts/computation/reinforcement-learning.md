---
type: concept
domain: computation
related_domains: [complexity]
provenance: mixed
status: developing
relates_to:
  - target: concepts/complexity/adaptation
    relation: instance-of
  - target: multi-agent-rl
    relation: foundation-for
  - target: neural-networks
    relation: used-in
  - target: concepts/complexity/fitness-landscapes
    relation: overlaps
tags: [reinforcement-learning, reward, policy, Q-learning, policy-gradient]
---

# Reinforcement Learning

> Learning through interaction with an environment: an agent takes actions, receives reward signals, and updates its policy to maximize cumulative reward — the computational formalization of adaptation through trial and feedback.

## Orientation

Reinforcement learning (RL) is the learning paradigm most directly connected to the adaptation mechanism at the core of CAS theory. Unlike supervised learning (which requires labeled examples) or unsupervised learning (which finds structure without feedback), RL learns from the consequences of actions in an environment. The agent must discover which actions lead to reward through exploration, rather than being told the right answer.

For this vault, RL is significant as the contemporary machine learning instantiation of Holland's adaptive agent and as the bridge between the adaptation thread and modern AI.

## Core

### The RL Framework

An RL agent interacts with an environment in discrete steps. At each step:
1. Agent observes state s
2. Agent selects action a according to its policy π(a|s)
3. Environment transitions to state s', returns reward r
4. Agent updates its policy based on (s, a, r, s')

The goal: find a policy that maximizes expected cumulative reward over time. The discount factor γ ∈ [0,1] determines how much future rewards are valued relative to immediate ones.

The **policy** π is the agent's behavioral schema — Holland's term maps directly. It specifies how the agent acts in each state. The **value function** V(s) estimates the expected cumulative reward from state s under the current policy — the agent's model of how good it is to be in each state.

### Core Algorithms

**Q-learning** (Watkins, 1989): Learn the action-value function Q(s,a) — the expected cumulative reward from taking action a in state s, then acting optimally. Q-learning is off-policy (learns the optimal policy regardless of which policy generated the data) and model-free (does not require a model of the environment). The update rule is:

```
Q(s,a) ← Q(s,a) + α[r + γ max_{a'} Q(s',a') - Q(s,a)]
```

**Policy gradient methods**: Directly optimize the policy parameters θ by gradient ascent on expected reward. REINFORCE, PPO (Proximal Policy Optimization), and SAC (Soft Actor-Critic) are the dominant modern policy gradient algorithms. Combined with neural network function approximation, these underlie AlphaGo, OpenAI Five, and most large-scale RL successes.

**Actor-critic methods**: Combine a policy (actor) with a value function estimate (critic) — the critic provides lower-variance gradient estimates for the actor. This is the architecture of most modern deep RL.

### Exploration vs. Exploitation

The fundamental tension in RL: the agent must exploit what it knows (take actions that have been rewarding) while exploring new actions (to discover whether they might be better). Too much exploitation leads to getting stuck at local optima. Too much exploration wastes time on known-bad actions.

This is the bandit problem generalized to sequential decisions. ε-greedy (take random action with probability ε) is the simplest solution. UCB (upper confidence bound) and Thompson sampling are principled alternatives. Curiosity-driven exploration (reward for visiting novel states) is the modern approach for sparse-reward environments.

### The Sparse Reward Problem and Connection to Evolution

RL with dense reward signals (frequent feedback) works well. RL with sparse rewards — where the agent gets feedback only rarely, after long sequences of actions — is much harder. The gradient signal is weak and delayed; the credit assignment problem (which actions were responsible for the reward?) becomes severe.

This is precisely the regime where evolutionary methods (neuroevolution, evolutionary strategies) often outperform gradient-based RL: when the reward landscape is too sparse for gradient information to be useful, population-based search over behavioral strategies can find solutions that RL cannot.

## Connections

**Adaptation** (`concepts/complexity/adaptation.md`) — RL is the computational formalization of adaptation through feedback; the policy is the schema, reward is fitness, the environment is the selective pressure.

**Multi-agent RL** (`concepts/computation/multi-agent-rl.md`) — multiple RL agents interacting; co-evolutionary dynamics, game theory, and emergent strategies.

**Neuroevolution** (`concepts/computation/neuroevolution.md`) — the evolutionary alternative to RL; gradient-free, works in sparse-reward settings, searches architecture as well as weights.

**Agent-based modeling** (`concepts/complexity/agent-based-modeling.md`) — RL agents in multi-agent environments are ABM agents with learning; the border between ABM and MARL is a design choice.

**Adaptation thread** (`synthesis/adaptation-thread.md`) — the full context for RL as an instance of the adaptation mechanism.

## Open Questions

- Is there a principled theory for when RL should be preferred over evolutionary search?
- Can RL agents in multi-agent environments develop the co-evolutionary dynamics (arms races, cooperation, symbiosis) seen in biological co-evolution?
- What is the right complexity science framing for transformer-based RL agents, where the policy is a sequence model rather than a Markov policy?
