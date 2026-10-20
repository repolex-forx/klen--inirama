# Repolex Knowledge Graph of klen/inirama

RDF knowledge graph data for [klen/inirama](https://github.com/klen/inirama), parsed by [repolex](https://repolex.ai).

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
rlex download klen/inirama
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3ec7c84b183b17a04aaf76e16f2a0ddf1c4633bb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3ec7c84b183b17a04aaf76e16f2a0ddf1c4633bb
│           └── chunk-001.nq.gz
├── blob
│   ├── 058c1fa59f55772c9bdd1a57406b95420f415259.nq.gz
│   ├── 080aec28d5e6995d77b0ed23cbc77b69440ebbdf.nq.gz
│   ├── 0c3a8e5885d67bda1212e4b6d7c5e195276a25ef.nq.gz
│   ├── 0f15ce18bbb1f099f5988672aefcc4661c072d98.nq.gz
│   ├── 1fd186eed315669ee324fb9a41966c64e27301fc.nq.gz
│   ├── 2437fd3c07225b1c5aafe48414cee7d1ac8a4b7c.nq.gz
│   ├── 2c6a57c37f744dbae4c7bfc649b05244f62e71ef.nq.gz
│   ├── 3370dc07efc1c84758290e2f1c6e2c6bbd09a0a1.nq.gz
│   ├── 43868a90a0d22fa97345fa82a231f09a1e610cc0.nq.gz
│   ├── 4aee971687c0f502d2ca3596fa4f25b0f6c14bb8.nq.gz
│   ├── 531f09cdf70fe6a4f5459ec3c7aaa8dfa568f8de.nq.gz
│   ├── 6651503cb59fa729a25f4ad0f60335c2652a1e8f.nq.gz
│   ├── 670525ac688639ae8b32978e2147e1fe9df568e5.nq.gz
│   ├── 6bc625b215eaca71f6d60abee0c565bc2bf39238.nq.gz
│   ├── 73a79cbf650cf18c3187018f926a97023edbda6a.nq.gz
│   ├── 891fe4301cb16ef60747b4d0d1a9e9b8ac8a986f.nq.gz
│   ├── 8f4d17d881256b91e625bbdfdbe6ecc47722f7fb.nq.gz
│   ├── 98461c16c0915f21e898697388b8c1241a249f73.nq.gz
│   ├── 9c109d6c2996df62801e682546c4da5706a02a8e.nq.gz
│   ├── abac3380026ee2a1d8f794cdbf9b22fdd35ae714.nq.gz
│   ├── ad79d0ca8f0c73adf83582c7077d7acc205fa42f.nq.gz
│   ├── b1b0a0cbe23b1002a776abf97699154a4e47f59a.nq.gz
│   ├── c0f5d71adce150652c019e2ca8326e9da77863ea.nq.gz
│   ├── d52cff549ef088711fc8c5b4f6d2570d96da5b71.nq.gz
│   └── dda2525fa1bbd4a7efa8c43a4e8424dadca47b74.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3ec7c84b183b17a04aaf76e16f2a0ddf1c4633bb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[klen/inirama](https://github.com/klen/inirama)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
