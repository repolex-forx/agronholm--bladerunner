# Repolex Knowledge Graph of agronholm/bladerunner

RDF knowledge graph data for [agronholm/bladerunner](https://github.com/agronholm/bladerunner), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/bladerunner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2f9a0c464090e23c92a29747fd20d7df5b770c08
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2f9a0c464090e23c92a29747fd20d7df5b770c08
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d17d312bb50611773ace065511599c98d02805c.nq.gz
│   ├── 0f6b8d828d068255785ac88b695739696fe6d06c.nq.gz
│   ├── 1834a2671a17bc35295b226d008f867215b69502.nq.gz
│   ├── 1d644e721a0c7032f4f9b1e4831efee8fd45ae05.nq.gz
│   ├── 1dcf502bbf4bbb70b22d69757ca24fce28c71ed7.nq.gz
│   ├── 33b0e6116b420dc01722fe554c32462b4e7321a0.nq.gz
│   ├── 36ce9f85ae8b3c90cea7a02f2465031697ed1583.nq.gz
│   ├── 3fe850f5587b2df61645e685e63b06cc240d72a1.nq.gz
│   ├── 554ee40c3008e54c80a72a22b70d126b882ed190.nq.gz
│   ├── 60d8489fbdeb61bc0e374344444f738d279aa8e9.nq.gz
│   ├── 64639a94c904988ea9c25d4efaa3ddffd80aeec0.nq.gz
│   ├── 68492b853b744ff47c799cb743d8f67e169c7143.nq.gz
│   ├── 692c789334676cd578e0d7649786dbdab4439e70.nq.gz
│   ├── 875d2f7d4557fa30cfac5f9aac9a91c1fffa7b87.nq.gz
│   ├── 9e170371c68c3a853df488e039deb653bff685ab.nq.gz
│   ├── 9f58e77b4db81489fc04a0e6ae1fe766f6269144.nq.gz
│   ├── aff1e27f5257041c16c12a3e822552def9a5087d.nq.gz
│   ├── d1be71eafe47b6a470a386a40d4d568f1b091f3a.nq.gz
│   ├── d5e849ddecc7b4108123887204da86cb620278aa.nq.gz
│   ├── d88db96831040c5a2d77912f49a21bfae66eaa7f.nq.gz
│   ├── dc3689b9160fb8477c7b6111610500b446a3e3d6.nq.gz
│   └── f8f3898900b29c63319637be8efb8bcdba914c89.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2f9a0c464090e23c92a29747fd20d7df5b770c08.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 28 files
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

[agronholm/bladerunner](https://github.com/agronholm/bladerunner)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
