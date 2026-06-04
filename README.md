# ComplexityNotes

> A knowledge base for tracing the intellectual history of complexity science — from its proto-scientific origins through the founding of the Santa Fe Institute and out into the disciplines where complexity concepts took root.

## Purpose

This vault exists to *find* complexity. The core complexity sciences condensed around SFI in the 1980s–90s and then largely dispersed into specific domains. The goal here is to maintain a unified map: tracing the threads that became complexity science, what they condensed into, and how they dispersed — so that a person or agent can see where ideas came from, how they connect, and where they live now.

The vault is designed for agent access. Documents are written with orientation at the top, substance in the middle, and explicit connections throughout. Frontmatter is machine-parseable. Relationships are stated in prose, not just linked.

## Agentic Use

This vault is structured under the discipline becoming known as **harness engineering** — shaping an agent's working context (memory, files, schemas, indexes) so a capable model can act usefully inside it. A vault legible only to humans forces an agent to reconstruct structure from prose on every read; a vault designed for both makes that structure explicit up front, and I have found it also has real value and raises interesting questions about information science.

- **Schema** — every node carries machine-parseable frontmatter (type, status, provenance, edges). Documented in `VAULT.md`; formal edge types in `schema/edges.yaml`.
- **Connections** — relationships are stated in prose *and* declared as edges in frontmatter, so the graph view and the reader's path stay consistent.
- **Indexing** — each `concepts/<domain>/INDEX.md` is both a human map and an agent entry point; same for `synthesis/` documents on cross-cutting threads.

**On authorship.** All content in this vault is original to the author or drawn from cited sources, with the exception of occasional LLM-assisted summaries of the author's own original material. Agentic involvement is restricted to the information-science work described above — structural refactoring, schema enforcement, indexing, link maintenance — not content generation.

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
