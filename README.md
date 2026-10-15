# Repolex Knowledge Graph of jupyter/testpath

RDF knowledge graph data for [jupyter/testpath](https://github.com/jupyter/testpath), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter/testpath
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5c6ccfda4db8ac9d5b89c304c1ede54a6d3d91c6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5c6ccfda4db8ac9d5b89c304c1ede54a6d3d91c6
│           └── chunk-001.nq.gz
├── blob
│   ├── 0cdf2495df4f400694b0533b97027451705be667.nq.gz
│   ├── 3834f5307043719949cc12862dd02cb89cd8187d.nq.gz
│   ├── 3a9c27fe2be75c9299048ac2c74719b7c90e479d.nq.gz
│   ├── 40e0c10e78ff89e9f163444867d2cb1c1bda08ed.nq.gz
│   ├── 46d0ff0093ea8d6478e671db3914b17c04fd76f4.nq.gz
│   ├── 4a94e98dc3953adf0b0ac8041a61fff2be0e2c07.nq.gz
│   ├── 5f19b8bcffdfbdf6d638a75f0e73252d5d0d12e0.nq.gz
│   ├── 675e6bf3743f3d3011c238657e7128ee9960ef7f.nq.gz
│   ├── 6966869c7054c18810eb323772b93ba5a42cefc5.nq.gz
│   ├── 6d9c211a90578b5f6a1048ca6c1abc518fa073bf.nq.gz
│   ├── 72e06414bab476a481e16fd536a4762da457aff8.nq.gz
│   ├── 7454dc655b8c90ba86812392365b8b3e2e116647.nq.gz
│   ├── 7ff0ab7037e9cea0244e422cb18e0b1775bd397a.nq.gz
│   ├── 803bbc179a14a6934be0d1030bb67b3b77fcd680.nq.gz
│   ├── 8e9fbdd05b21c8b707b35fed9328aa08ad7136aa.nq.gz
│   ├── 9d20ec19abf011f2d70652ad84c03c5c389661a0.nq.gz
│   ├── aa78ff6d1f728ce04c9700ecd9206adbb0bef0ad.nq.gz
│   ├── b1487b7819e7286577a043c7726fbe0ca1543083.nq.gz
│   ├── c1b45f7c9dd3fb2c088c65b617c842ade9e9371e.nq.gz
│   ├── c38885c33b427b3273c96b4800b80bd6df3d9320.nq.gz
│   ├── c804baec97721ecf55eb60c5c880c26437055a7c.nq.gz
│   ├── c82a16b164f332ac2e3e8e1297d1d4bc0834088f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e95629f10731722f0b1c19cdd7e35136b5e5d8b2.nq.gz
│   ├── f08b218837ca913d58b1c36439e7ff2ef78a9cb0.nq.gz
│   ├── f44e3552299c25983a6d02359a79e39b068c1fdd.nq.gz
│   ├── f5acc2adf484156086c2e4e18612f0d363d76c1f.nq.gz
│   └── fa545effd5f91cd86038511d514414c9f5cf866b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5c6ccfda4db8ac9d5b89c304c1ede54a6d3d91c6.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 36 files
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

[jupyter/testpath](https://github.com/jupyter/testpath)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
