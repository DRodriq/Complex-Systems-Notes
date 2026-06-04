---
type: concept
name: "Compositional Game Theory"
domain: category-theory
related_domains: [computation, applied]
status: stub
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Compositional Game Theory

> A reformulation of game theory in which a game with strategies is itself a morphism — an **open game** — that composes with other open games to build larger games. Introduced by Ghani, Hedges, Winschel, and Zahn (2018), the framework uses lens-like structures to represent the bidirectional flow of plays and payoffs, recovering Nash equilibria as fixed-point conditions on the composite.

## Orientation

Classical game theory treats games monolithically: define a set of players, strategies, payoffs, and analyze them as one object. Compositional game theory turns each game into an *open* structure with input/output interfaces, so games compose by plugging interfaces together. The categorical machinery — built on lenses — makes the equilibrium conditions of a composite game expressible from the equilibrium conditions of its parts, and supports a graphical notation for plays and counter-plays.

## Core

(stub — to be filled when this node develops)

## Connections

- Built on [[lenses-and-optics]] as the bidirectional substrate.
- Generalized by [[categorical-cybernetics]] (the `Para(Optic)` construction subsumes both open games and gradient-based learners).
- Connects category theory to mainstream [[concepts/applied/economics/INDEX|economics]] and game-theoretic [[concepts/applied/social-science/cooperation|cooperation]] models.
- Active development around the [[institutions/cybernetics-institute]] (UK), where Hedges and collaborators are based.

## Sources

- [[sources/papers/ghani-hedges-compositional-game-theory-2018]] — *Compositional Game Theory* (LICS 2018); the founding paper.
- [[sources/papers/capucci-categorical-cybernetics-2021]] — `Para(Optic)` generalization unifying games with learners and agents.
