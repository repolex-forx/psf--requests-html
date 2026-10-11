# Repolex Knowledge Graph of psf/requests-html

RDF knowledge graph data for [psf/requests-html](https://github.com/psf/requests-html), parsed by [repolex](https://repolex.ai).

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
rlex download psf/requests-html
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 075ac162dc62fc532037df0d98954ab840a97516
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 075ac162dc62fc532037df0d98954ab840a97516
│           └── chunk-001.nq.gz
├── blob
│   ├── 00bf847d1b55d4e63b5a3f73df3188ca9f8dad21.nq.gz
│   ├── 1c4b3dcba71d5ef6fcf00766506dfc542f2d3e69.nq.gz
│   ├── 2a2f5ffa54a18bc116ed6a7bce900c586ce91786.nq.gz
│   ├── 357cadea08ba10e5fe8c09ea16895d99ebada305.nq.gz
│   ├── 3b8830d5d4d5a6825b1e699641391e2f4d3125ad.nq.gz
│   ├── 3f3912c3052a066c8d53834018ede5b934c1d9d8.nq.gz
│   ├── 42903c46d0fa6f51a557e492d79bfa8713da0da6.nq.gz
│   ├── 4a9df7654ff8a8dbc361f1381a7a4e6f3da97eaa.nq.gz
│   ├── 5237a82bf1c3ee1f5a1fb15728607492a44164e1.nq.gz
│   ├── 5fb9fe5d1ab72a616113bf2bedfa3d55d348ac2c.nq.gz
│   ├── 613bbdfa75f8521108f3f344838ec891a9fa771c.nq.gz
│   ├── 6b5a7021951834555fde8bc59645603a49d5aa25.nq.gz
│   ├── 78b0d967df6272e64476ebbee598fd8b2ce2446b.nq.gz
│   ├── b145ee2bc9e122e1b117b343c678da9482d72692.nq.gz
│   ├── b2c56edd682a7f98125c2137238f4365e8cd6fa8.nq.gz
│   ├── bbb1515293c2320d5f02bf2450baf8437ac37ea3.nq.gz
│   ├── ca8dea653246467337f5678aa6c5c9853f68ae32.nq.gz
│   ├── cd341def55064270d7ac582d629ff5c4670af761.nq.gz
│   └── e6dc6652aeb54557a09f433ced778ed93ec0b387.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 075ac162dc62fc532037df0d98954ab840a97516.nq.gz
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

[psf/requests-html](https://github.com/psf/requests-html)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
