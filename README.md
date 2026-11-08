# Repolex Knowledge Graph of bentoml/simple_di

RDF knowledge graph data for [bentoml/simple_di](https://github.com/bentoml/simple_di), parsed by [repolex](https://repolex.ai).

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
rlex download bentoml/simple_di
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 427b7f53f66d244a85887ae015d739709cf68a9d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 427b7f53f66d244a85887ae015d739709cf68a9d
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 544b7027f9dbd21bd27f8fc933b709be66e9074f.nq.gz
│   ├── 856e98d8b66d4149115b10844b8f5dd0451a37f0.nq.gz
│   ├── 8d1e2f1e8978d78db45123733d33995b7f1140f3.nq.gz
│   ├── a11c06cd9d17d79b9b001329a1f722ad90d96846.nq.gz
│   ├── c60a78c46854faed9f857e85259aa5be05b42848.nq.gz
│   ├── d8fd6a3320adb6c657af92053fa98d07fbd9c050.nq.gz
│   ├── e4af425327d1099b7c973e19638702b2c76bcbd2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f4bba22c9f4dfbd6d744f2c5e7228d824c97f208.nq.gz
│   ├── f92794e4276e54229c3ad73ececda5fca05a64dc.nq.gz
│   ├── f929f707e091b02eec368e1a7d0b5390bd47055a.nq.gz
│   └── ff07e50cf4bece9fda19bf1eb6762cc59b790bee.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 427b7f53f66d244a85887ae015d739709cf68a9d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[bentoml/simple_di](https://github.com/bentoml/simple_di)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
