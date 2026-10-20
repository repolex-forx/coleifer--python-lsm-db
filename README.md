# Repolex Knowledge Graph of coleifer/python-lsm-db

RDF knowledge graph data for [coleifer/python-lsm-db](https://github.com/coleifer/python-lsm-db), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/python-lsm-db
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c375670648386485e42540f251fff03767e9808b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c375670648386485e42540f251fff03767e9808b
│           └── chunk-001.nq.gz
├── blob
│   ├── 002d1b93c6f31187db78e898311d42cbc3991965.nq.gz
│   ├── 09f9338488ca92bd2fa86eef8b14b039a19c78d8.nq.gz
│   ├── 1156dae80463fd710d80ea8604d1ba3887d4d7d6.nq.gz
│   ├── 13dd9fe312c8f5882c71f250847a63b59b9291fb.nq.gz
│   ├── 1a199fc1ce52782c64d77217c5d36bee64622a64.nq.gz
│   ├── 3dcef42f701bc27279d23604a48cfbc00650428e.nq.gz
│   ├── 449429d21ad6ca4c827ec1425d20505ddf2eec9d.nq.gz
│   ├── 48701c4c5e45eb1d79e33ec3bd07da9f27d0d1e5.nq.gz
│   ├── 4e3c5e59ce0977a9038aba67be71882d5b35a6f1.nq.gz
│   ├── 54810e15215bddfd91eb2be1e86ba4d0a5e2e393.nq.gz
│   ├── 5feba1f320b466dcff1db27d0db0a16b8c834fa8.nq.gz
│   ├── 64de63018868fb873bf3a00f93c6f1de6ba29587.nq.gz
│   ├── 69c39fd3f5cfe429882ab58573b7d4b891605a84.nq.gz
│   ├── 6c5d06b4c8e1db924b592fb480cb9da533bc5a6b.nq.gz
│   ├── 7ba2d20e2cfd940c3e7983f6a7aa59d4135d7a53.nq.gz
│   ├── 85e4a0fc9edf39fc123ea4284aaa9e117cd38991.nq.gz
│   ├── 88952d15fc721ac19747a0cf284b7f7b28520c45.nq.gz
│   ├── 960e87915d14ec9d74e351f088b62e5724c0cd01.nq.gz
│   ├── 9b1b63cee248afaecb3e48d5bee20b83c539a883.nq.gz
│   ├── 9f4144618af803b83b1de22d013713125b13488f.nq.gz
│   ├── a72c8cafb28b2ccd6b3cbfcba4f347d82a8b9699.nq.gz
│   ├── b6ba04f0a0eab8b73abeeca31befd265bab5f4dd.nq.gz
│   ├── b6fd74cf9aa5ac2cf26a58438881465af18f6bf9.nq.gz
│   ├── babb1d06630e1ede9ea67debf41a7eb410795f62.nq.gz
│   ├── c56df3a11e14f1229acf4b5038694abd2e5157f0.nq.gz
│   ├── cb99b2a61e23a10d7c3c627f8bb0994ff5f757fe.nq.gz
│   ├── dbfa1a61ff8e8a09575f2f2229cc3058b14ca142.nq.gz
│   ├── df141479cecaad0223b97fdff70dd76c625f5b74.nq.gz
│   ├── e22f3e8d8a847a9770fa7e555eab161ac18b64a1.nq.gz
│   ├── e3bb60417726d07b3c2416ce52ecbfc4eb6349b4.nq.gz
│   ├── f2b353105a508b291b3d952adbaabb600a7473eb.nq.gz
│   └── f690e3b0630fa05023c84d318af62286c8ee5c19.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c375670648386485e42540f251fff03767e9808b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 40 files
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

[coleifer/python-lsm-db](https://github.com/coleifer/python-lsm-db)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
