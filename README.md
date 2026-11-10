# Repolex Knowledge Graph of devxoul/Then

RDF knowledge graph data for [devxoul/Then](https://github.com/devxoul/Then), parsed by [repolex](https://repolex.ai).

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
rlex download devxoul/Then
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 21910ae00ddbb5378338bb288460cdd838f897df
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 21910ae00ddbb5378338bb288460cdd838f897df
│           └── chunk-001.nq.gz
├── blob
│   ├── 4f273435bef71326a042d25ba7320e03827dfd59.nq.gz
│   ├── 596598fc2ab29d4602ceef52cfaf50a1fc6c946f.nq.gz
│   ├── 7f0cb52c6d4a56746a25095cf2bca06c05ba2151.nq.gz
│   ├── 8649b9b3f8e1069c7fcb132e9c897361e42685d0.nq.gz
│   ├── 897bdaf89c0cfac54d0011a688d50022410da023.nq.gz
│   ├── 94d072301b92f6def7eddaa0b1bf4f006b34a400.nq.gz
│   ├── 9a633ec04e89e415c8efaace689e2ebb27de500e.nq.gz
│   ├── 9f8365d8085c2b131d969ce4f84d47cc03fb0020.nq.gz
│   ├── a36894767154b4da9eebcc9a9a6dc0a579561157.nq.gz
│   ├── a45303d7f870fa5106878afced830d00ba5fceab.nq.gz
│   └── b1848ec93580a8419749206680999487604f7132.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 21910ae00ddbb5378338bb288460cdd838f897df.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[devxoul/Then](https://github.com/devxoul/Then)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
