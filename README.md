# Repolex Knowledge Graph of google-deepmind/learning-to-learn

RDF knowledge graph data for [google-deepmind/learning-to-learn](https://github.com/google-deepmind/learning-to-learn), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/learning-to-learn
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f3c1a8d176b8ea7cc60478bfcfdd10a7a52fd296
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f3c1a8d176b8ea7cc60478bfcfdd10a7a52fd296
│           └── chunk-001.nq.gz
├── blob
│   ├── 038e66a8985a049c4191a695597fd74789028606.nq.gz
│   ├── 06c7bf08d59751f076e2b07a314dc77781a7205a.nq.gz
│   ├── 08fcee978863c7096955ae73c1e416d63d93ca23.nq.gz
│   ├── 102063cf4c7262144e1e2406e38f580c7c9a017d.nq.gz
│   ├── 145c0ceb50a8792cd425bc7f455aab118220dbaa.nq.gz
│   ├── 1a09deb2d3e38931e5b9463399a9f36fc0d92667.nq.gz
│   ├── 2d9d86eafc3eb689eff1a67fce16d2e5664fd3a9.nq.gz
│   ├── 49b38c79e7a6607c26843f18f4ac9030e92ab23e.nq.gz
│   ├── 53cb5ed8496ffa09b83e836a3f988e2131700e88.nq.gz
│   ├── 553556f7b88635d69c65556904baa42655fc0321.nq.gz
│   ├── 592cfbfb77b3d625edf1bd334b4bfa0f2d3c05c6.nq.gz
│   ├── 95bf9bb1a64b499e0ed00589ee85e484b0698baa.nq.gz
│   ├── c0bb694235687fb7fa23e75d6ce9eecc596099b5.nq.gz
│   ├── c4f2880ea692e95e62eb7da53f17e18aedabc1d7.nq.gz
│   └── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f3c1a8d176b8ea7cc60478bfcfdd10a7a52fd296.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[google-deepmind/learning-to-learn](https://github.com/google-deepmind/learning-to-learn)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
