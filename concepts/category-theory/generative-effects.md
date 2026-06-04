---
type: concept
name: "Generative Effects"
domain: category-theory
related_domains: [complexity, philosophy]
status: stub
provenance: literature
extends: []
instance_of: []
contrasts_with: []
---

# Generative Effects

> The precise technical term, introduced in Fong & Spivak's *Seven Sketches in Compositionality* (Ch. 1), for a **functor failing to preserve joins** (or more generally, colimits): $F(a \vee b) \neq F(a) \vee F(b)$. The whole has a property the parts lack — emergence, formalized as a map failing to commute with composition.

## Orientation

The canonical example is graph connectivity: take the connected-components functor from graphs to sets. Joining two disjoint graphs can create a connecting path that neither had alone, so the connected-components of the join is not the join of the components. The functor *fails to preserve the join*, and that failure is precisely the "extra" structure that emergence consists of. Fong & Spivak's contribution is the recognition that this pattern — *a functor failing to commute with colimits* — is the right formal home for many discussions of emergence that had previously been informal.

## Core

(stub — to be filled when this node develops)

## Connections

- A central object of [[applied-category-theory]] and the technical anchor for compositional treatments of emergence.
- The structure-vs-behaviour split in [[open-systems]] turns on which functors *do* preserve composition (rate equation, black-boxing) and which do not (long-run qualitative behaviour) — generative effects are the latter.
- Cited as the bridge between categorical machinery and the [[concepts/complexity/emergence|emergence]] discussions in [[concepts/philosophy/emergence|philosophy of complex systems]].

## Sources

- [[sources/books/fong-spivak-seven-sketches-2018]] — Ch. 1; the original definition and graph-connectivity example.
- [[sources/papers/fong-algebra-open-systems-2016]] — formal development in the decorated-cospan setting.
