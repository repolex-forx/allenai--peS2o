# Repolex Knowledge Graph of allenai/peS2o

RDF knowledge graph data for [allenai/peS2o](https://github.com/allenai/peS2o), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/peS2o
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cc4800ffd798bb9baa29552059b294073cf91e90
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cc4800ffd798bb9baa29552059b294073cf91e90
│           └── chunk-001.nq.gz
├── blob
│   ├── 0771666e4723262f6052350c85ab95dfefee18f7.nq.gz
│   ├── 07f002ecaeb4c8e9d4d57a5580dd47ba4e8579ff.nq.gz
│   ├── 13239b4b59dcf900879f37a0779c01254490d05b.nq.gz
│   ├── 1b19957b097444bc89a84d66157aeaaa1c998579.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 3136f3179cba8149f4ad3fbb31c460cab09c2a62.nq.gz
│   ├── 433040315a6fe500e88fb90a62b7db0d072307d3.nq.gz
│   ├── 5742569104c0bea935423a41c7e99372d1d98ab1.nq.gz
│   ├── 5a63956fb77cb677d876de92b9698c74cf568950.nq.gz
│   ├── 88d3cf93c274e94ddcb908f56a140318d95bc2bd.nq.gz
│   ├── 896d5e47a54d6361e8914522b0afa80bc2df7246.nq.gz
│   ├── 8ec268eef41047412d4a504bb2e72dfc699c0595.nq.gz
│   ├── 9f3a01d66234079981c43b95007696184ba9a246.nq.gz
│   ├── a0f17a5592a1e1a37668d3406170a4dff86cc617.nq.gz
│   ├── a1b8dfbe8f333749689b1c01d4a6bb9baf37f557.nq.gz
│   ├── df02f4af3bf2314f17ecdca5a6d55a0e1f23b027.nq.gz
│   └── faf814be727ae608d833633be4c1aad3ad14ef52.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cc4800ffd798bb9baa29552059b294073cf91e90.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[allenai/peS2o](https://github.com/allenai/peS2o)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
