# Repolex Knowledge Graph of simonw/symbex

RDF knowledge graph data for [simonw/symbex](https://github.com/simonw/symbex), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download simonw/symbex
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 81c4b9c042f271f0d8b9a4d50095876cd54e05a2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 81c4b9c042f271f0d8b9a4d50095876cd54e05a2
│           └── chunk-001.nq.gz
├── blob
│   ├── 1654300be0f6898cd4885d2ac333f8ec502fd64e.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 53605b7a5ec51bc95dca4fb43fdb350bf9362435.nq.gz
│   ├── 586b21ccc629ee7600b36fe634350318f3baf5fc.nq.gz
│   ├── 5cff8d4b35e23a6eb08739be892402cc78651723.nq.gz
│   ├── 7afd7e616cffa522f27f46925c4131b52a8258e4.nq.gz
│   ├── 90ef1213467fe00ecb064636ba46a16dcff11ca9.nq.gz
│   ├── 95f6cb9de96c2a9596aa41e81114817939eb90c0.nq.gz
│   ├── 98dcca0c2836ae53d67260be8a5431b855e461bb.nq.gz
│   ├── 9cb5fde40f0e26093cb33b9ca73306c058b290c9.nq.gz
│   ├── a3218301421fa865356103bd33d744f009ec7330.nq.gz
│   ├── aec3d9722bff5c065534f228830c511176cc808c.nq.gz
│   ├── b0bca065ccf0719ab4459eda54294b66062b0abe.nq.gz
│   ├── ba5b2fee6c2fed40b9d3d0b03f4c0a14dc7e87e1.nq.gz
│   ├── bb3ea54d66efbc5f2b7f3cb3601e3736a2408e23.nq.gz
│   ├── bff9873bcaa61d2df8a8c104b17dabf4a53dbc36.nq.gz
│   ├── d8cf22a0c2622fca213dbc9de7c64148b7337fb3.nq.gz
│   ├── e5b96fa7f76509907eefd33c97463acf921d9366.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 81c4b9c042f271f0d8b9a4d50095876cd54e05a2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[simonw/symbex](https://github.com/simonw/symbex)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
