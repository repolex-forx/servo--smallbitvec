# Repolex Knowledge Graph of servo/smallbitvec

RDF knowledge graph data for [servo/smallbitvec](https://github.com/servo/smallbitvec), parsed by [repolex](https://repolex.ai).

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
rlex download servo/smallbitvec
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ad9b17eace931eb8190fa25f7775932ed48d370f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── ad9b17eace931eb8190fa25f7775932ed48d370f.nq.gz
│   └── repolex
│       └── ad9b17eace931eb8190fa25f7775932ed48d370f
│           └── chunk-001.nq.gz
├── blob
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 22b6d843a69302b3a272db0a478d7caf0cb8b723.nq.gz
│   ├── 43ac5359dcc616af5b183836ee4e90035f62cc9d.nq.gz
│   ├── 56119321b48eef694544da50bf0973e8299eeab8.nq.gz
│   ├── a1906c0217a5e0bf1d558a0868cd2194d86bba4b.nq.gz
│   ├── a9d616611de000fbc5e8dd5720c3df0198b80961.nq.gz
│   ├── cb20da01a2187bb7ff2eec46fc2171125e2c477f.nq.gz
│   ├── ceddb9035ba003c50cf7c26cf8bd94546e0048f1.nq.gz
│   ├── dea1a6a4056af45b81a247800ec83de573e64fef.nq.gz
│   └── eccd7b4ab85ef538f952b87de4948f2b1e6997d6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── ad9b17eace931eb8190fa25f7775932ed48d370f.nq.gz
├── filetree
│   └── ad9b17eace931eb8190fa25f7775932ed48d370f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 20 files
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

[servo/smallbitvec](https://github.com/servo/smallbitvec)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
