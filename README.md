# Repolex Knowledge Graph of pytest-dev/pytest-freezer

RDF knowledge graph data for [pytest-dev/pytest-freezer](https://github.com/pytest-dev/pytest-freezer), parsed by [repolex](https://repolex.ai).

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
rlex download pytest-dev/pytest-freezer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d6fcf3856b8fd20c11a172bb329c432d708d5e80
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d6fcf3856b8fd20c11a172bb329c432d708d5e80
│           └── chunk-001.nq.gz
├── blob
│   ├── 3d8d92b09313027f605ede3da44e58ac6b4780a8.nq.gz
│   ├── 5a5de99b552d387c9617b4826108969f0f5de22c.nq.gz
│   ├── 8b2ed274a3156b474fd14e2f597237d62028fde7.nq.gz
│   ├── 990e98f007251992537aa13f6a87c58db33abc19.nq.gz
│   ├── a5035299e842d516b36747fa528a8a3c8eceb2b7.nq.gz
│   ├── c6481d5f740462ec9fd3edcb32aa56806e316c77.nq.gz
│   └── c8444181ed0b61023b5e4fed5ed8820b4db10d47.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d6fcf3856b8fd20c11a172bb329c432d708d5e80.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[pytest-dev/pytest-freezer](https://github.com/pytest-dev/pytest-freezer)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
