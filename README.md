# Repolex Knowledge Graph of tox-dev/tox-gh

RDF knowledge graph data for [tox-dev/tox-gh](https://github.com/tox-dev/tox-gh), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/tox-gh
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8f3f27176e75d702b4fabddc7a4082da55117984
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8f3f27176e75d702b4fabddc7a4082da55117984
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f9e29ba8c2dadd452306034fef7602da9e07023.nq.gz
│   ├── 364982344fbd94d55705e1f27a9a87abaa255333.nq.gz
│   ├── 366bf3f0420c71f72b49528bbbe715fd3d829db8.nq.gz
│   ├── 4802a98a8b7504ada6d6875b0ab58df5e8de2ad9.nq.gz
│   ├── 4f27bbeea01b69bdec4209adaa5b83b5fe383078.nq.gz
│   ├── 5f89818f9e63c2f6829c7706c57f223cdb5bbd38.nq.gz
│   ├── 6060133627af98388fc24349ec7f5f110b299a19.nq.gz
│   ├── 69d0cfd202c019ca1d5a92d59faf9a1380c61930.nq.gz
│   ├── 7beb007f589d6d3dd9643713bd518163193d42c6.nq.gz
│   ├── 8f146aede79a870b1d6d656075656d7ade1dc8c0.nq.gz
│   ├── 8fc54a492d48644a840d978452000e7924050238.nq.gz
│   ├── a571de09ab87287b11b7d0aefbf51707a1f88b2d.nq.gz
│   ├── a61b6a861a58af88ada9ff42a6d31c932951d118.nq.gz
│   ├── a8d9ce0dd54a2d26eff1b01bd4390fe4d4175768.nq.gz
│   ├── c792f1303917a09991cabd6fe2e49c1d9b714bf2.nq.gz
│   ├── de995a3a21503f37c9efde746e55e8101e698f72.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed7bfe1cf25071e76fc4383246ab075ad94f902b.nq.gz
│   ├── ef0ad8b2dbd8c5d2b39f0752ea54c3843c4fd20f.nq.gz
│   └── f9babf096233f2928e985b0ce76eaaaf266a9ddc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8f3f27176e75d702b4fabddc7a4082da55117984.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[tox-dev/tox-gh](https://github.com/tox-dev/tox-gh)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
