---
type: concept
domain: philosophy
related_domains: [complexity, dynamics, information]
status: developing
relates_to:
  - target: complex-adaptive-systems
    relation: foundation-for
  - target: self-organization
    relation: overlaps
  - target: reductionism
    relation: contrasts
  - target: effective-complexity
    relation: measured-by
tags: [emergence, philosophy, core, contested]
---

# Emergence

> The claim — contested but practically indispensable — that complex systems exhibit properties at the collective level that are not straightforwardly present in, or predictable from, their components.

## Orientation

Emergence is the conceptual center of gravity for complexity science. Nearly every phenomenon the field studies — flocking, market dynamics, consciousness, self-organization, adaptive behavior — is described as emergent. But the concept is poorly defined, typically invoked by example rather than criterion, and carries both a weak reading (collective properties are hard to predict) and a strong reading (collective properties are genuinely ontologically novel) that most researchers conflate or quietly choose between.

For this vault, emergence is treated as an open problem rather than a solved one. The goal is to accumulate enough precision to distinguish useful from empty uses of the concept, and to connect the philosophical debate to the empirical and mathematical work across the other domains.

## Core

### The Definition Problem

Emergence is not well defined and not agreed on. Definitions tend to cluster around a set of common themes — irreducibility, unpredictability, conceptual novelty, ontological novelty, supervenience — without specifying which of these is necessary or sufficient. David Pines' formulation from SFI: "collective phenomena or behaviors in complex adaptive systems that are not present in their individual parts." This captures the intuition but does no philosophical work — "not present" is exactly the contested question.

The closest to a rigorous definition in the literature: emergence as *information at a higher level of description that does not exist at the lower level*. This is analytically cleaner but empirically problematic, because it is not obvious that the information truly does not exist at the lower level rather than merely not being expressed or accessible there.

### Weak and Strong Emergence

The distinction that does the most work in the literature is between **weak emergence** (the collective property is in principle derivable from the components and their interactions, but is computationally or practically irreducible — you have to run the system to find out) and **strong emergence** (the collective property cannot in principle be derived, representing genuine downward causation or ontological novelty).

Most working scientists implicitly accept weak emergence — they use agent-based models precisely to generate and study it. Strong emergence is philosophically contested and empirically unverified. The strongest candidate cases (consciousness, life) are also the hardest to analyze.

### Personal Working View

The intuition that "emergence" is sometimes obfuscation deserves to be taken seriously. Nonlinear dynamical systems give us many cases where strikingly complex behavior is latent in simple equations — the information is not absent from the system description, it just isn't apparent without analysis or simulation. To call the output "emergent" risks mystifying what is really a tractable mathematical question about where complexity lives in a system's structure.

The more useful question may be: *why are some systems better analyzed as wholes rather than decomposed into parts?* This reframes emergence as an epistemological question about the right level of description rather than an ontological claim about novelty. It connects to information theory (when does aggregation lose or hide information?) and to dynamical systems (when do interactions produce behavior that cannot be inferred from subsystems in isolation?).

### Historical Arc

The concept traces at minimum to Aristotle ("the whole is more than the sum of its parts") but serious modern treatment begins with the British Emergentists in the early 20th century (C. D. Broad, Samuel Alexander), who distinguished emergent from resultant properties. The concept then receded in philosophy under the dominance of logical positivism and reduction-friendly mid-century physics, resurfacing in the 1970s–80s alongside nonlinear dynamics, systems biology, and eventually complexity science. Anderson's "More is Different" (1972) is the pivot point in physics — the argument that each level of complexity requires its own principles and is not derivable from the level below.

## Connections

**Reductionism**: Emergence is the primary challenge to the reductionist program. But the relationship is not simple opposition — weak emergence is fully compatible with ontological reductionism (everything is physics) while being practically incompatible with explanatory reductionism (you can't explain ant colony behavior by describing individual ants). See `concepts/philosophy/reductionism.md`.

**Self-organization**: Self-organization is the *process* that produces emergent structures — the mechanism side of emergence. Where emergence asks "what is this property?", self-organization asks "how did it get here?". See `concepts/complexity/self-organization.md`.

**Complex adaptive systems**: The CAS framework is built around emergent collective behavior. Emergence is what the SFI program is ultimately trying to explain and formalize. See `concepts/complexity/complex-adaptive-systems.md`.

**Effective complexity**: Gell-Mann and Lloyd's effective complexity is one of the few attempts to give emergence a quantitative handle — measuring the length of the schema that captures a system's regularities, excluding both pure order and pure randomness. See `concepts/information/effective-complexity.md`.

**Neural networks as dynamical systems**: The question of whether trained neural networks exhibit anything like emergence — whether their learned representations are genuinely novel relative to the training process — is an open and active question that sits at the intersection of this concept and computation.

## Sources

- `sources/books/bedau-humphreys-emergence-2008.md` — anthology of key philosophical and scientific papers; the standard academic reference
- `sources/papers/anderson-more-is-different-1972.md` — the physics argument for emergence as a real phenomenon; highly influential
- `sources/articles/pines-emergence-unifying-theme.md` — SFI's framing of emergence as the 21st century science theme

## Open Questions

- Is there a quantitative criterion that cleanly separates emergent from non-emergent properties?
- Does effective complexity capture what matters, or does it miss the dynamic/process dimension?
- What is the relationship between computational irreducibility (Wolfram) and emergence?
- Can weak emergence be given a precise information-theoretic definition that makes it empirically testable?
