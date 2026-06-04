---
type: person
name: "Yaneer Bar-Yam"
active_period: [1984]
domain: complexity
related_domains: [information, applied, dynamics]
status: developing
provenance: mixed
trained_under: []
affiliated_with: [necsi, mit-physics]
founded: [necsi]
participated_in: []
coined: [complexity-profile, complexity-mismatch]
---

# Yaneer Bar-Yam

> Physicist and complexity scientist who founded NECSI in 1996. Developed the complexity profile as a formal tool for measuring complexity across scales, and applied it to failures in healthcare, education, military command, and management.

## Role and Contributions

Bar-Yam (MIT PhD, physics, 1984) founded the New England Complex Systems Institute in 1996 as a research and education center focused on a formal, application-oriented approach to complex systems, explicitly independent of SFI.

His major theoretical contribution is the **complexity profile**: a curve showing how much information is needed to describe a system as a function of the scale of observation. This framework grounds his applied concept of **complexity mismatch** — the claim that systems fail when the complexity of the managing entity (at each scale) doesn't match the complexity of what it's trying to manage. Both ideas derive from renormalization group methods in physics, which he generalizes to social and biological systems.

He wrote two books: *Dynamics of Complex Systems* (1997), a graduate-level mathematical treatment, and *Making Things Work* (2004), an applied treatment for policy and management audiences.

## How He Defines "Complex Systems"

The following definition is essentially unchanged from his 1997 textbook through his 2020 review paper (Siegenfeld & Bar-Yam):

> "Complex Systems is a new approach to science studying how relationships between parts give rise to the collective behaviors of a system, and how the system interacts and forms relationships with its environment."

Key structural features:
- The unit of analysis is **relationships between parts**, not the parts themselves
- The object of explanation is **collective behavior**
- **Interaction with the environment** is part of the definition, not optional

He gives the same cross-scale examples in every context: the brain (neurons → mind), social systems (people → organizations), molecules (atoms → matter), weather (air flows → climate). This is not illustrative but load-bearing — his whole point is that the same framework applies across all of them.

His orienting argument against reductionism: physics and biology have each made progress by decomposing things into parts, but "forgot what they were trying to do" — the relationships between parts, which is what generates the behaviors we actually care about.

## How He Defines "Complexity"

Two related definitions, both from information theory:

- **Description-based:** complexity is the minimal length of a description of the system (Shannon information / Kolmogorov complexity)
- **Time-based:** complexity is the minimal time required to create the system (computational complexity)

Formalized in Siegenfeld & Bar-Yam (2020): C = log₂N, where N is the number of possible behaviors the system can exhibit.

The key tool is the **complexity profile** — complexity as a function of scale. Three canonical system types:
- **Random** (independent parts): high fine-grained complexity, collapses at coarse scale (a gas)
- **Coherent** (all parts in lock-step): flat complexity curve across all scales (a cannonball, a marching army)
- **Complex** (partially correlated subgroups): gradually declining curve (a human, a corporation)

A fundamental tradeoff: reducing interdependence among parts increases their individual fine-scale complexity but decreases large-scale collective complexity. There is a conservation law — you can't have it both ways.

## How He Frames "Complex Systems Science"

> "As a discipline, complex systems is a new field of science studying how parts of a system and their relationships give rise to the collective behaviors of the system, and how the system interrelates with its environment."

> "The standard assumptions that underlie many conceptual and quantitative frameworks do not hold for many complex physical, biological, and social systems. Complex systems science clarifies when and why such assumptions fail and provides alternative frameworks for understanding the properties of complex systems."
> — Siegenfeld & Bar-Yam (2020) — the opening framing by 2020

He organizes the field into three interrelated approaches, consistent across 2002–2004:
1. **How interactions give rise to patterns of behavior** — self-organization, emergence
2. **The space of possibilities** — complexity profiles, what configurations are accessible
3. **Adaptive/evolutionary processes** — how systems select effective behaviors

The methodological spine is the **renormalization group** (Wilson, 1970s), a physics technique for identifying which variables matter at a given scale by systematically coarse-graining. Bar-Yam explicitly names this as his core method — he generalizes it to complex systems broadly, producing his multiscale representation framework.

## Vocabulary

Terms he uses consistently across all texts:

| Term | Function |
|---|---|
| Complexity profile | Complexity as function of scale — his signature concept |
| Scale | The organizing variable; not just size but level of description |
| Multiscale | Behaviors occurring at multiple levels simultaneously |
| Relationships | His unit of analysis (not the parts themselves) |
| Patterns of behavior | How collective dynamics manifest |
| Space of possibilities | The full set of states a system can exhibit |
| Emergence / self-organization | Collective properties not reducible to parts |
| Interdependence | What makes parts inseparable; the central feature |
| Renormalization group | His methodological grounding in physics |
| Complexity mismatch | Applied version: when system and task complexities don't match |
| Distributed/networked control | Alternative to hierarchy for high-complexity environments |

Terms he avoids or uses sparingly:
- **"Complex adaptive systems"** — the SFI signature term; he uses "complex systems" without the "adaptive" modifier as his primary term, treating adaptation as a feature of some systems rather than the defining one
- **"Chaos"** as a synonym for unpredictability — he explicitly says "complex systems science has more to tell us than just that the world is unpredictable"

## Positioning

### vs. SFI
SFI's central concept is **complex adaptive systems** (CAS), a term originating with Holland and Gell-Mann, emphasizing agents, adaptation, and evolution as the defining features of complex systems. Bar-Yam's frame is broader and more formal: adaptation is one process within the space of complex systems phenomena, not the organizing concept. His mathematical framework (complexity profile, renormalization group) is more formal than SFI's characteristic tools (agent-based modeling, genetic algorithms, qualitative emergence). NECSI's structure also differed institutionally — explicitly oriented toward education and policy application from the outset, grounded in New England university faculty rather than SFI's itinerant visiting scholars model.

### vs. physics
His tools come from physics but his claim is that collective behaviors require their own science, not reducible to physics. Physics made the error of thinking that understanding elementary particles was the same as understanding nature at all scales.

### vs. traditional mathematics
He frames complex systems as requiring tools beyond calculus and statistics, which "got the wrong answers" for real-world systems because they fail under nonlinear dependency and network effects.

## Evolution Over Time

The framing is **strikingly stable** from 1997 to 2020 — the same definition, examples, and three-approach structure appear across all texts. What changed:

- **The complexity profile becomes the organizing center**: By 2020 (Siegenfeld paper), it is the first principle from which efficiency/adaptability tradeoffs, requisite variety, and mismatch are all derived. In 2002 it was one tool among several.
- **The "standard assumptions fail" framing becomes the opening move**: By 2020 this is the disciplinary position statement; earlier texts built toward it inductively.
- **Application confidence deepens**: The Staatslabor interview (2020) shows the same vocabulary applied to pandemic control and policy with two decades of practice behind it.

## Key Works
- *Dynamics of Complex Systems* (1997) — [[bar-yam-dynamics-complex-systems-1997]]
- *Making Things Work* (2004) — [[bar-yam-making-things-work-2004]]
- "General Features of Complex Systems" (EOLSS/UNESCO, 2002)
- Siegenfeld & Bar-Yam, "An Introduction to Complex Systems Science and Its Applications," *Complexity* (2020)

## Connections
Connects to [[new-england-complex-systems-institute]], [[multi-scale analysis]], [[complexity mismatch]], [[renormalization group]], [[information theory]], and applied complexity in policy, healthcare, and governance. Positioned in explicit contrast to [[santa-fe-institute]] framing.

## Open Questions
- How does he relate to chaos theory precisely? His 1997 textbook covers chaos as background, but he resists chaos = unpredictability. Where does chaos sit in his taxonomy?
- His relationship to Ashby's Law of Requisite Variety — he cites this as grounding for complexity mismatch but how explicit is the connection in his own texts?
- Are there earlier papers (pre-1997) where the complexity profile concept first appears?
