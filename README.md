# Repolex Knowledge Graph of celery/bootsteps

RDF knowledge graph data for [celery/bootsteps](https://github.com/celery/bootsteps), parsed by [repolex](https://repolex.ai).

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
rlex download celery/bootsteps
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f2e788edb182d54037c5f2b9fad28dc81f701f8e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f2e788edb182d54037c5f2b9fad28dc81f701f8e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e3be623f5a772d15eb4c81f9da76f524aa6316c.nq.gz
│   ├── 16a83da6ed34bfc907baecbfa603b6d83e640097.nq.gz
│   ├── 17069323ca1ab9c887bb92c1646a6bc4b8a20766.nq.gz
│   ├── 2ef12fe33c06121d911bb40507e7e6f164d06e8b.nq.gz
│   ├── 33d97369254b965c3e9cf4f013af3a4d8de32a96.nq.gz
│   ├── 34abaf2123b0874dd559738c633638d6ca60ad3c.nq.gz
│   ├── 3ea3c81d97a8ca7b53a8d64f2423e50f451a44d6.nq.gz
│   ├── 4f3fe5a430e69d0dedf5cff9e22183da6d977785.nq.gz
│   ├── 5efdea7e03cf17e4f69036ea14b20549b6a15505.nq.gz
│   ├── 5f4a13a225db317dbb3f4cb3ca1e5dc5b10eec2a.nq.gz
│   ├── 8396721f64bc59a5cfddd64b585d56ddc698c1a6.nq.gz
│   ├── 86e08d98fc31304fe63aea0928e057734c0765bb.nq.gz
│   ├── 8d187394bd96938772ce4bbbdb4e78287c3da350.nq.gz
│   ├── 94f2d3a60eb434fd707531392b00ebd941fa96e0.nq.gz
│   ├── bde40719bd3535ad07d3e9f8e8533d00174a975c.nq.gz
│   ├── cfc30ca6802807cfa04dde39d0026d4ddcc6ff78.nq.gz
│   ├── dbf04ace6a2c0e722c304b6359694004938284fa.nq.gz
│   ├── e5bde9f42b9eeaa18828bc21d7fe32b63b665d52.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f00ffee27618b227fc083f021aa26cc8363e0399.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f2e788edb182d54037c5f2b9fad28dc81f701f8e.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 27 files
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

[celery/bootsteps](https://github.com/celery/bootsteps)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
