# Repolex Knowledge Graph of samuelcolvin/tinicly

RDF knowledge graph data for [samuelcolvin/tinicly](https://github.com/samuelcolvin/tinicly), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/tinicly
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2486fa3ea42a1f53397ce97b0a201f22fbf12d47
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2486fa3ea42a1f53397ce97b0a201f22fbf12d47
│           └── chunk-001.nq.gz
├── blob
│   ├── 0640d980e43d12671ba77655a874b3e202a39a82.nq.gz
│   ├── 1b40929afc7fda8ad38060b57f82b7acb1d7cd88.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 29b89b9084d3c160f4fb4b2d1133d5c919db8a31.nq.gz
│   ├── 3359023e02559c4e43dff6ab55563bfe1bf2d314.nq.gz
│   ├── 6050ceb7dd2dab15085841a79eeb6076821ac753.nq.gz
│   ├── bc6edc524d8ce9ea33f9f093146ba8f07eb7af20.nq.gz
│   ├── bf110f1102e35a9647413c032adedace0ff31f58.nq.gz
│   └── c6fc301e8adcf33c7d9c5ad574a57befb5a93807.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2486fa3ea42a1f53397ce97b0a201f22fbf12d47.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[samuelcolvin/tinicly](https://github.com/samuelcolvin/tinicly)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
