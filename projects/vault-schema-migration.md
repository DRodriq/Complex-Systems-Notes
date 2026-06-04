---
type: project
name: "Vault Schema Migration"
status: in-progress
---

# Vault Schema Migration

Migrating the vault from an ad-hoc linking structure to a typed graph schema that supports both human reading and machine extraction.

## What's Done

- `VAULT.md` — schema section replaced with typed frontmatter templates per node type, slug naming convention, and pointer to edges.yaml
- `schema/edges.yaml` — formal edge definitions: direction, valid node types, declared_on convention
- `people/yaneer-bar-yam.md` — updated to new schema (working example)
- `sources/books/bar-yam-*` — updated to new schema (working examples)

## Outstanding

**Migration of legacy directories**
- `Books/`, `Papers/`, `People/`, `Institutions/` use human-friendly title-case filenames
- New files in `sources/`, `people/`, `institutions/`, `concepts/` use slug convention
- A script should crawl legacy dirs, extract frontmatter, generate slugs, rename files, update internal wikilinks
- Do not do this by hand

**Concept nodes**
- `key_concepts` fields reference concept slugs that don't have files yet (e.g. `complexity-profile`, `complexity-mismatch`, `multi-scale-analysis`)
- Concept files should be created as concepts are discussed — don't batch-create stubs
- Extraction tool should handle dangling references gracefully (log, don't fail)

**Remaining node types to template**
- Most existing `sources/books/` files still have old-style frontmatter (human name in author field, key_concepts as freetext)
- Update opportunistically as files are touched, not all at once

## Schema Reference

See `VAULT.md` and `schema/edges.yaml`.
