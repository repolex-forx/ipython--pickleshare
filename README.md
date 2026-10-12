# Repolex Knowledge Graph of ipython/pickleshare

RDF knowledge graph data for [ipython/pickleshare](https://github.com/ipython/pickleshare), parsed by [repolex](https://repolex.ai).

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
rlex download ipython/pickleshare
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9f0a267b02063bc01bd8a44c54909dab62a590a8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9f0a267b02063bc01bd8a44c54909dab62a590a8
│           └── chunk-001.nq.gz
├── blob
│   ├── 086f84f6eae948965ee5022a04f917e450458d66.nq.gz
│   ├── 3c6e79cf31da1c0433d2fa666bf50b53f6359f26.nq.gz
│   ├── 480c137fc5c9bce022acfc51d556b6442b9fd2f8.nq.gz
│   ├── 52c3866086332c014f964f5cb4749423215c131b.nq.gz
│   ├── 53afb18c9ef1f9a80142d7294b177775b0e8bcdf.nq.gz
│   ├── 76ab20c8bc79d9edba05d8fe5aaeacc0890c51dc.nq.gz
│   ├── a7e8ea5ed256c70b9be0fea010d7f4195d6241af.nq.gz
│   ├── c4c870879b1c698ff9b791ecb5da8fc3848e363c.nq.gz
│   ├── c5b40f13e26be345532810003dd27eefd2f94b35.nq.gz
│   └── e8f60c3ecd031106e2bc79034690f3bff2eebfcb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9f0a267b02063bc01bd8a44c54909dab62a590a8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[ipython/pickleshare](https://github.com/ipython/pickleshare)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
