# Repolex Knowledge Graph of asottile/flake8-2020

RDF knowledge graph data for [asottile/flake8-2020](https://github.com/asottile/flake8-2020), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/flake8-2020
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7c8c9ac8a96336a8fe540538ca3b10e4956318a0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7c8c9ac8a96336a8fe540538ca3b10e4956318a0
│           └── chunk-001.nq.gz
├── blob
│   ├── 2375625110fd8b0b8f973edfe45ccab994fcc904.nq.gz
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 5370c9485451439199ab7ab9ba30c95d9a046275.nq.gz
│   ├── 5a4128de7f16972c216a66cf8d9b13716c1b6111.nq.gz
│   ├── 5bdd50e53efa3c0f05787078f0056b24f04e38a7.nq.gz
│   ├── 6e20be810b6719b4c884fd46c75836291e88324a.nq.gz
│   ├── 8c38c3fa07daab3596dae959bfec1e3571868cb0.nq.gz
│   ├── 9b21c7136e13bfdf43feef39a42bbf3ac4dea55a.nq.gz
│   ├── bda8bfe38f48beb0b43a79ba611b2fe6683caf61.nq.gz
│   ├── ca1d90ea180858ae143c0e62d920e350d3acc62d.nq.gz
│   ├── d3cc19d5ec04e7eebff9eb549818ab4f5fb8afe4.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7c8c9ac8a96336a8fe540538ca3b10e4956318a0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[asottile/flake8-2020](https://github.com/asottile/flake8-2020)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
