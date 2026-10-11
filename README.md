# Repolex Knowledge Graph of marshmallow-code/marshmallow-select

RDF knowledge graph data for [marshmallow-code/marshmallow-select](https://github.com/marshmallow-code/marshmallow-select), parsed by [repolex](https://repolex.ai).

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
rlex download marshmallow-code/marshmallow-select
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ca00c071d0de1c688dd508b6101ffdc389e48892
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ca00c071d0de1c688dd508b6101ffdc389e48892
│           └── chunk-001.nq.gz
├── blob
│   ├── 49c76a3401ce46c3a2844205d3951439484d2f2a.nq.gz
│   ├── 577871c7523b8dcd348b9e3dd49147421033e552.nq.gz
│   ├── 5a8e332545f667aab9bf3a17f11dba27c70b656a.nq.gz
│   ├── 62bbe3b5126341ede44ea2d7eab34d0c96dde2d6.nq.gz
│   ├── 63c11bd0fab53341cd6465f9cf38134a5e49e661.nq.gz
│   ├── 76a7738e43b5de24119f3b44ac27985eff129744.nq.gz
│   ├── 8283048a61a276635c818eefb5de18d634ea3586.nq.gz
│   ├── 8aabbe3b7486025454bccaeb1fc628bf1d0866f0.nq.gz
│   ├── 94349ae1e33cf34c7c907628ed538e12d4acd25b.nq.gz
│   ├── b5fa91d310d7993b213e45df5d15492cb5cfcd31.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ec8dfc30b91b3b6a0ac4fe33ab5740b714d177dc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ca00c071d0de1c688dd508b6101ffdc389e48892.nq.gz
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

[marshmallow-code/marshmallow-select](https://github.com/marshmallow-code/marshmallow-select)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
