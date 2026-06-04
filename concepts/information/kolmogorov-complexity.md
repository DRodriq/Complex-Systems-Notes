---
type: concept
domain: information
related_domains: [computation]
provenance: mixed
status: developing
relates_to:
  - target: shannon-entropy
    relation: contrasts
  - target: logical-depth
    relation: foundation-for
  - target: effective-complexity
    relation: foundation-for
  - target: concepts/dynamics/lyapunov-exponents
    relation: overlaps
tags: [Kolmogorov, algorithmic-information, compression, Chaitin, incompressibility]
---

# Kolmogorov Complexity

> The length of the shortest program that produces a string on a universal Turing machine — a measure of algorithmic information content that captures how much description an object requires, independent of any probability distribution.

## Orientation

Kolmogorov complexity (also called algorithmic information content or descriptive complexity) is the algorithmic counterpart to Shannon entropy. Where Shannon measures average uncertainty across a source distribution, Kolmogorov measures the intrinsic information content of a specific object. A string is simple if it has a short program; it is complex if the shortest program is approximately as long as the string itself. The concept was developed independently by Kolmogorov, Chaitin, and Solomonoff in the 1960s.

## Core

### Definition

The Kolmogorov complexity K(x) of a binary string x is the length (in bits) of the shortest program p such that a universal Turing machine U halts on input p and outputs x:

```
K(x) = min{|p| : U(p) = x}
```

K(x) is defined relative to a universal Turing machine U, but the choice of U changes K(x) by at most a constant (the size of a translator between any two universal machines). So K(x) is universal up to an additive constant — a machine-independent property of x up to that constant.

### Incompressibility

Random strings have high Kolmogorov complexity. A random string of length n cannot be described by any program shorter than n bits — no compression is possible because there is no pattern to exploit. By counting argument: there are 2ⁿ strings of length n but fewer than 2^{n-c} programs of length less than n-c, so most strings are incompressible.

Highly structured strings have low Kolmogorov complexity: π to a billion digits has a short program (the algorithm for computing π); the all-zeros string has a program of length O(log n).

### Uncomputability

K(x) is not computable. Given a string x, you cannot algorithmically determine the length of the shortest program that produces it — this is equivalent to the halting problem. You can compute upper bounds (by running programs and seeing which produce x), but not the exact value.

This makes Kolmogorov complexity a theoretical tool rather than a practical one. In practice, compression algorithms (gzip, bzip2, LZ77) provide computable upper bounds on K(x), and compressed file size is used as a proxy. This proxy is rough but often useful.

### Algorithmic Probability

Solomonoff's variant uses the **algorithmic probability** P(x) = Σ_{p:U(p)=x} 2^{-|p|} — the probability that a random program produces x. Short programs contribute more. This is the foundation of Solomonoff induction — the theoretically optimal universal prediction method, which is also incomputable.

### Why It Fails as a Complexity Measure

Like Shannon entropy, Kolmogorov complexity ranks random strings as maximally complex. An incompressible random string has K(x) ≈ n — the maximum possible complexity. But random strings are not complex in the sense complexity science cares about: they carry no organized information, no regularities, no structure that reflects a long computational history.

This is the same failure as Shannon entropy but from the algorithmic direction. Both measures conflate incompressibility (random) with organized complexity (living cell, economy). Logical depth and effective complexity are the attempts to fix this.

## Connections

**Shannon entropy** (`concepts/information/shannon-entropy.md`) — the statistical counterpart; Shannon measures average coding length for a source, Kolmogorov measures the description length of a specific object. For typical strings from a source, K(x) ≈ H(source) per bit.

**Logical depth** (`concepts/information/logical-depth.md`) — Bennett's fix: measure how long it takes to generate x from its shortest description, not how long the description is.

**Effective complexity** (`concepts/information/effective-complexity.md`) — Gell-Mann's fix: separate the schema (structured part) from the random component; measure only the schema length.

**Measuring complexity thread** (`synthesis/measuring-complexity-thread.md`) — the sequence of why Kolmogorov complexity was developed and why it needed to be extended.

## Sources

- Kolmogorov (1965), "Three approaches to the quantitative definition of information" — not yet in vault sources
- Chaitin (various) — randomness and incompleteness

## Open Questions

- Are there practically computable approximations to Kolmogorov complexity that preserve its theoretical properties well enough for empirical complexity science?
- Does the incomputability of K(x) limit its usefulness in biology, or are order-of-magnitude estimates sufficient?
