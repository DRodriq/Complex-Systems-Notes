---
type: source-paper
author: [Lim, Bryan]
year: 2022
status: queued
domain: computation
key_concepts: [quality-diversity, reinforcement learning, skill repertoires, robotics, evolutionary computation, MAP-Elites]
---

# Dynamics-Aware Quality-Diversity for Efficient Learning of Skill Repertoires — Lim, Grillotti, Bernasconi, Cully (2022)

> A paper introducing a dynamics-aware quality-diversity algorithm for more efficiently learning diverse repertoires of robot behaviors by incorporating system dynamics into the search process.

## Key Contribution
Lim et al. extend quality-diversity algorithms (particularly MAP-Elites) by making them dynamics-aware, using learned forward models of robot dynamics to predict outcomes of candidate behaviors before evaluating them. This dramatically improves sample efficiency in skill repertoire learning for robotics applications.

## Vault Relevance
Connects to [[quality-diversity optimization]] and [[evolutionary robotics]] threads; relates to [[antoine-cully]] and the QD optimization literature.
