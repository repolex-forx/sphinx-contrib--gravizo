# Repolex Knowledge Graph of sphinx-contrib/gravizo

RDF knowledge graph data for [sphinx-contrib/gravizo](https://github.com/sphinx-contrib/gravizo), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/gravizo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f248b433e588593312fc1423516dd950944d0801
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f248b433e588593312fc1423516dd950944d0801
│           └── chunk-001.nq.gz
├── blob
│   ├── 02d5c4dfcf2d5c1ba014e06203e6aa289602df83.nq.gz
│   ├── 13222258e2a9b6432c4c6926632f6797fe69c1c5.nq.gz
│   ├── 1995d59ce57f9ab256db41d7e768c0e46e8852cb.nq.gz
│   ├── 1d45dc6ea30fb622e1c50396757105770b0b9685.nq.gz
│   ├── 432708da31c31f1008372128b83e65abdc0035ae.nq.gz
│   ├── 55ff9de50d6ca483766e6c2f6c04990de5eb12df.nq.gz
│   ├── 6fe2156bea0116d4a1383fe9ebadd4c2eab550cd.nq.gz
│   ├── 7c993e484ae3fda1ff8c54cf585b805af8f8dca3.nq.gz
│   ├── 8acdd82b765e8e0b8cd8787f7f18c7fe2ec52493.nq.gz
│   ├── a8323592fbeb7a4bd0d7704ec4ef273eddc1311d.nq.gz
│   ├── ae0f862b865ef2f17cee6a962d8fb480d7229488.nq.gz
│   ├── ae98854869d2388673f4ff3e490a49bd596f7667.nq.gz
│   ├── b18546cfbc6ff19148e8f35340cddf9d8fc65ebc.nq.gz
│   ├── b4f72101d3f10af187f1257861def6330c327174.nq.gz
│   ├── bc6df17a0d95ea0153cc71c79e7c3209faa3509e.nq.gz
│   ├── f7fce8751c7cf5519b1dcbeff315939f47ea406f.nq.gz
│   └── fe28f4b545c2a4159f6cdb5543a6f162aa8316f8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f248b433e588593312fc1423516dd950944d0801.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 24 files
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

[sphinx-contrib/gravizo](https://github.com/sphinx-contrib/gravizo)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
