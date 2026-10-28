# Repolex Knowledge Graph of PennyLaneAI/flagsynth

RDF knowledge graph data for [PennyLaneAI/flagsynth](https://github.com/PennyLaneAI/flagsynth), parsed by [repolex](https://repolex.ai).

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
rlex download PennyLaneAI/flagsynth
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f117326f7bf9c847da495993caadd3bcd767bd9d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f117326f7bf9c847da495993caadd3bcd767bd9d
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2e4d1370f4eb585bc8548c9057899a016f1becb6.nq.gz
│   ├── 370252459dbc8487f53edd9a3fbf2354935c0d6a.nq.gz
│   ├── 3b98c7878f7702f4b56089cdbd756437bffc8dde.nq.gz
│   ├── 48f8e9830db8cf0b5f6a3ee8d74fb571b8d7dbe9.nq.gz
│   ├── 4da5c81f3a495d043fa342173273cd92988f93ab.nq.gz
│   ├── 5e5d886413a7f41893bdf7e6d0397f924dc73689.nq.gz
│   ├── 955e3a6183e3df23ae79eb386d02fe966f34fb96.nq.gz
│   ├── 98b66930d748b0ca9bbae6a009cebc73512bd4e0.nq.gz
│   ├── a088d6ae20bd9a0d88b8ca50230d3bbea72dc8fc.nq.gz
│   ├── af17e520a0ec05a946d7290f5cec8775d3d93ab9.nq.gz
│   ├── b4e92923d011c2fcb658d8fd8b9fdb0c6de77a81.nq.gz
│   ├── bedd03f91e151317773af6550b57cdf1fc7495df.nq.gz
│   ├── c3526b7dd34a362d7e2bcf7d24005aea06b0ea8d.nq.gz
│   ├── d44ae809d6dbeb28059cffa55b4f02f4356a077c.nq.gz
│   ├── ddea7a76b339b83689a9413c8cded478f2c64d34.nq.gz
│   ├── ecbce9ab1db7a13083ab358564a4c9450a319710.nq.gz
│   ├── fb500ef435ce2064db029d9b5f79d5bf99cdecae.nq.gz
│   └── fbcb974db0f2c99ed6e93a83b82f697e4abdd1a3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f117326f7bf9c847da495993caadd3bcd767bd9d.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 26 files
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

[PennyLaneAI/flagsynth](https://github.com/PennyLaneAI/flagsynth)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
