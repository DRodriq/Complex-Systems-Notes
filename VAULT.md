---
type: vault-index
status: mature
---

# ComplexityNotes Vault

> A knowledge base for tracing the intellectual history of complexity science — from its proto-scientific origins through the founding of the Santa Fe Institute and out into the disciplines where complexity concepts took root.

## Purpose

This vault exists to "find" complexity. The core complexity sciences condensed around SFI in the 1980s–90s and then largely dispersed into specific domains. The goal here is to maintain a unified map: tracing the threads that became complexity science, what they condensed into, and how they dispersed — so that a person or agent can see where ideas came from, how they connect, and where they live now.

The vault is designed for agent access. Documents are written with orientation at the top, substance in the middle, and explicit connections throughout. Frontmatter is machine-parseable. Relationships are stated in prose, not just linked.

## Major Intellectual Threads

These threads run across domains and are the primary connective tissue of the vault. Each has a synthesis document.

**Adaptation** — How systems learn, evolve, and improve without central direction. Runs from Darwin through Holland's genetic algorithms, Kauffman's fitness landscapes, and CAS theory into reinforcement learning and evolutionary computation. The foundational question: what is the mechanism of adaptation, and is it universal?
→ `synthesis/adaptation-thread.md`

**Emergence and Self-Organization** — Where does structure come from in systems with no architect? Runs from Prigogine's dissipative structures through Kauffman's self-organization, Langton's artificial life, and into agent-based modeling and network formation. Philosophically contested; practically indispensable.
→ `synthesis/emergence-and-self-organization-thread.md`

**Scaling and Power Laws** — Universal quantitative patterns that appear across biology, cities, companies, and networks regardless of substrate. West's metabolic scaling, Barabasi's scale-free networks, Zipf's law. The question of why the same mathematics describes such different systems.
→ `synthesis/scaling-thread.md`

**Computation and Dynamics** — The relationship between computation and physical dynamics. Wolfram's cellular automata, the edge of chaos as a regime of maximal computation, neural networks as dynamical systems, the Turing/Church thesis meeting nonlinear dynamics. What does it mean for a physical process to "compute"?
→ `synthesis/computation-and-dynamics-thread.md`

**Measuring Complexity** — The problem of quantifying what we mean by complex. Shannon entropy, Kolmogorov complexity, Gell-Mann/Lloyd's effective complexity, logical depth. None fully satisfying; together they triangulate something real.
→ `synthesis/measuring-complexity-thread.md`

## Directory Map

```
VAULT.md                        ← you are here

/concepts/                      ← primary knowledge layer
  /complexity/                  ← CAS, emergence, self-organization, adaptation
  /dynamics/                    ← nonlinear dynamics, chaos, attractors, bifurcation
  /computation/                 ← neural nets, genetic algorithms, cellular automata, RL
  /networks/                    ← network science, scale-free, community structure
  /information/                 ← information theory, complexity measures
  /philosophy/                  ← emergence, reductionism, ontology
  /applied/                     ← domain applications
    /ecology/
    /economics/
    /social-science/

/synthesis/                     ← cross-cutting threads, the connective tissue

/sources/
  /books/                       ← book-length sources
  /papers/                      ← journal papers and articles
  /journals/                    ← journal reference entries
  /articles/                    ← blog posts and web articles

/people/                        ← person nodes: role, contributions, connections
/institutions/                  ← SFI, NECSI, and peer institutions
/projects/                      ← active project notebooks
```

## Navigation Guide

**Entering by topic:** Start at the relevant domain `INDEX.md` in `/concepts/`. It gives a map of the domain and entry points into individual concept notes.

**Entering by thread:** Go directly to the relevant file in `/synthesis/`. These are written as coherent essays tracing a single cross-cutting idea across domains.

**Entering by source:** Files in `/sources/books/` and `/sources/papers/` summarize individual works and link to the concept nodes they inform.

**Entering by person:** Files in `/people/` describe a figure's role, contributions, and which concept nodes their work feeds into.

**Drilling deeper:** Every concept note has a `Sources` section pointing to specific books, papers, or people, and a `Connections` section stating relationships to other concepts in prose.

## Schema Reference

### Naming Convention

All files use hyphenated slug IDs that double as node IDs in frontmatter references. The filename without `.md` is the canonical node ID — use it verbatim in edge fields.

| Node type | Pattern | Example |
|---|---|---|
| person | `lastname-firstname` | `bar-yam-yaneer` |
| source-book | `lastname-shorttitle-year` | `bar-yam-dynamics-1997` |
| source-paper | `lastname-shorttitle-year` | `barabasi-scaling-networks-1999` |
| concept | `concept-name` | `complexity-profile` |
| institution | `institution-shortname` | `santa-fe-institute` |
| event | `shortname-year` | `sfi-economy-workshop-1987` |
| journal | `journal-shortname` | `complexity-journal` |

### Frontmatter by Node Type

**person**
```yaml
type: person
name: "Full Name"
active_period: [YYYY, YYYY]    # single-element [YYYY] if still active
domain: primary-domain
related_domains: []
status: stub | developing | mature
provenance: literature | synthesis | mixed
trained_under: []              # → person
affiliated_with: []            # → institution
founded: []                    # → institution
participated_in: []            # → event
coined: []                     # → concept
```

**source-book**
```yaml
type: source-book
title: "Full Title"
author: []                     # person slugs — canonical edge for authorship
edited_by: []                  # person slugs — for collected volumes
year: YYYY
status: queued | reading | read
domain: primary-domain
related_domains: []
cites: []                      # → work
key_concepts: []               # → concept
published_by: slug             # → institution
```

**source-paper**
```yaml
type: source-paper
title: "Full Title"
author: []                     # person slugs
year: YYYY
status: queued | reading | read
domain: primary-domain
related_domains: []
cites: []                      # → work
key_concepts: []               # → concept
published_in: slug             # → journal
```

**concept**
```yaml
type: concept
name: "Concept Name"
domain: primary-domain
related_domains: []
status: stub | developing | mature
provenance: literature | synthesis | mixed
extends: []                    # → concept
instance_of: []                # → concept
precedes: []                   # → concept (this is an ancestor of)
contrasts_with: []             # → concept
```

**institution**
```yaml
type: institution
name: "Full Name"
founded_year: YYYY
dissolved_year: YYYY           # omit if active
location: "City, Country"
domain: primary-domain
funded_by: []                  # → institution
spawned: []                    # → institution
```

**event**
```yaml
type: event
name: "Event Name"
date: YYYY                     # or [YYYY, YYYY] for ranges
event_type: workshop | conference | lecture-series | symposium
hosted_by: []                  # → institution
part_of: []                    # → event (series)
```

**journal**
```yaml
type: journal
name: "Journal Name"
domain: primary-domain
published_by: slug             # → institution
```

### Edge Definitions

Formal edge schema with direction and valid node types lives at `/schema/edges.yaml`. The extraction tool loads this as its type system — frontmatter fields not in edges.yaml are ignored.

**Convention:** edges are declared on the `from` node. Two exceptions for readability: `author` and `edited_by` are declared on the work (the `to` node) because that is the natural place to write them. The schema file flags these with `declared_on: to` so the tool handles them correctly.

### Status Levels

- `stub` — frontmatter and title only, or minimal content
- `developing` — orientation and partial core written, not yet complete
- `mature` — orientation, core, connections, and sources all present
- Works only: `queued` | `reading` | `read`

### Provenance Levels

```yaml
provenance: literature   # content tracks primary sources; stable, citable
provenance: synthesis    # vault author's interpretation; living, will grow
provenance: mixed        # core is literature-grounded; connections are synthesis
```

Source notes are always `literature`. Synthesis documents are always `synthesis`. Concept and person notes are typically `mixed`.

### Section Epistemic Convention

| Section | Epistemic status |
|---|---|
| `## Core` | Literature-grounded — what the sources establish; treat as reliable |
| `## Connections` | Vault author's synthesis — interpreted relationships; treat as informed hypothesis |
| `## Personal View` | Vault author's intellectual stance; not a claim about the field |
| `## Open Questions` | Speculation and prompts for investigation; treat as starting points |
| `## Orientation` | Summary framing — may blend both; read as introduction, not authoritative claim |

**This distinction matters.** The synthesis and personal view sections are where the vault is most alive and most subjective. The sources layer is the stable foundation; the synthesis layer is the interpretive structure built on top of it — valuable and developed, but the vault author's construction.

## Notes on Vault State

The vault is actively being built and has accumulated over years through a single person's study. It carries that history: some entries are incomplete, some connections are speculative, some framings reflect a particular path through the material rather than the field's consensus view. This is not a flaw to correct — the vault is partly an intellectual portrait, and that perspective is part of its value. Read it accordingly.

Source and person nodes are stubs first, filled in as the concept nodes that draw on them develop. Synthesis documents are the highest-value layer and will grow the most over time.
