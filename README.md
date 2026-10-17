# Repolex Knowledge Graph of openai/CLIP

RDF knowledge graph data for [openai/CLIP](https://github.com/openai/CLIP), parsed by [repolex](https://repolex.ai).

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
rlex download openai/CLIP
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d05afc436d78f1c48dc0dbf8e5980a9d471f35f6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d05afc436d78f1c48dc0dbf8e5980a9d471f35f6
│           └── chunk-001.nq.gz
├── blob
│   ├── 06083ef9a613b5d360e87c3f395c2a16c6e9208e.nq.gz
│   ├── 0a66286b7d5019c6e221932a813768038f839c91.nq.gz
│   ├── 1043f2389d3aa8dde666036ce7221bea2cce6754.nq.gz
│   ├── 232b7792eb97440642547bd462cf128df9243933.nq.gz
│   ├── 321f181f917b03529a05fc27aee81a0bd6fba32d.nq.gz
│   ├── 398a6282cc243e449430d91c2562491fc799929d.nq.gz
│   ├── 4cd096005c8e5777e0706d97d182c3bd87b651a9.nq.gz
│   ├── 4e97f0b45803b7c04ae89548934af4f257a97501.nq.gz
│   ├── 520b354b62ab4d199d49462e9c65890d924c69e6.nq.gz
│   ├── 6d8aaf7b13f04031e7ea00d58a1c131b98bdfe20.nq.gz
│   ├── 6db1ca46f0706d2276e0c95578f4aa4dc0136e58.nq.gz
│   ├── 7449d9d72abe92700628c9cd318e5577c43fe0d0.nq.gz
│   ├── 7aa5c505446480df9bbd28abb909fd53809fb387.nq.gz
│   ├── 7b5088a527f720063f044eb928eee315f63b2fc0.nq.gz
│   ├── a1b5ec9171fd7a51e36e845a02304eb837142ba1.nq.gz
│   ├── d27454caf046d8d699f87b8cb8404a05e488dbef.nq.gz
│   ├── db56b56e29258cc871fe0e6297bde00436d9180b.nq.gz
│   ├── dba7fb654f4bed7adff1da1e7d4297670ea51469.nq.gz
│   ├── dcc5619538c0f7c782508bdbd9587259d805e0d9.nq.gz
│   ├── e083ffba84e3bc3c43ad236dc748b38d6b2174d4.nq.gz
│   ├── effd8d995ff1842a48c69d2a0f7c8dce4423d7a2.nq.gz
│   └── f2c6fd4fe9074143803e0eb6c99fa02a47632094.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d05afc436d78f1c48dc0dbf8e5980a9d471f35f6.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[openai/CLIP](https://github.com/openai/CLIP)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
