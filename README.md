# Repolex Knowledge Graph of Kozea/RadicaleStorageByIndex

RDF knowledge graph data for [Kozea/RadicaleStorageByIndex](https://github.com/Kozea/RadicaleStorageByIndex), parsed by [repolex](https://repolex.ai).

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
rlex download Kozea/RadicaleStorageByIndex
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3325886e3e75d9b8924a1b8fc44b396fc611b722
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3325886e3e75d9b8924a1b8fc44b396fc611b722
│           └── chunk-001.nq.gz
├── blob
│   ├── 43e9ba512b51ee97315b25c7ef233eafae210616.nq.gz
│   ├── 5a6ed24630365ac3393a386041c5832dc0ae5521.nq.gz
│   ├── 7c09649ca807f266027323770fd5ab5b3e4eeef5.nq.gz
│   ├── 7c0a543e1436d6e9c20a3e4268edee28a985205e.nq.gz
│   ├── 8e0e6bb0eeba7945949310a5634f8c3e411c5f8e.nq.gz
│   ├── ac890d34dd56e5e5b445ac9097a91e9cea982376.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3325886e3e75d9b8924a1b8fc44b396fc611b722.nq.gz
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

[Kozea/RadicaleStorageByIndex](https://github.com/Kozea/RadicaleStorageByIndex)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
