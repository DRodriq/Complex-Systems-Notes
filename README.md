# ComplexityNotes

> A knowledge base for tracing the intellectual history of complexity science — from its proto-scientific origins through the founding of the Santa Fe Institute and out into the disciplines where complexity concepts took root.

## Purpose

This vault exists to *find* complexity. The core complexity sciences condensed around SFI in the 1980s–90s and then largely dispersed into specific domains. The goal here is to maintain a unified map: tracing the threads that became complexity science, what they condensed into, and how they dispersed — so that a person or agent can see where ideas came from, how they connect, and where they live now.

The vault is designed for agent access. Documents are written with orientation at the top, substance in the middle, and explicit connections throughout. Frontmatter is machine-parseable. Relationships are stated in prose, not just linked.

## Major Intellectual Threads

Each has a synthesis document in `synthesis/`:

- **Adaptation** — How systems learn, evolve, and improve without central direction. Darwin → Holland → Kauffman → RL.
- **Emergence and Self-Organization** — Where structure comes from in systems with no architect. Prigogine → Kauffman → Langton → ABM.
- **Scaling and Power Laws** — Universal quantitative patterns across biology, cities, companies, networks. West, Barabasi, Zipf.
- **Computation and Dynamics** — Wolfram, edge of chaos, neural nets as dynamical systems.
- **Measuring Complexity** — Shannon, Kolmogorov, Gell-Mann/Lloyd. None fully satisfying; together they triangulate something real.

## Directory Map

```
VAULT.md                        ← schema, conventions, full directory map

/concepts/                      ← primary knowledge layer (by domain)
/synthesis/                     ← cross-cutting threads; connective tissue
/sources/{books,papers,journals,articles}/
/people/                        ← person nodes
/institutions/                  ← SFI, NECSI, and peers
/projects/                      ← active project notebooks
/schema/                        ← formal edge-type definitions
```

## Entry Points

- **By topic** — start at the relevant `concepts/<domain>/INDEX.md`
- **By thread** — go directly to the relevant file in `synthesis/`
- **By source** — `sources/books/` and `sources/papers/` summarize works and link to concepts
- **By person** — `people/` describes a figure's role and which concept nodes their work feeds
- **First time?** — `synthesis/getting-started.md` (a practical guide) or `synthesis/why-complexity.md` (the case for the project)

## For Schema and Conventions

See [`VAULT.md`](VAULT.md) — frontmatter specs by node type, edge definitions, status/provenance conventions, and the section-epistemic convention (Core vs Connections vs Personal View).
