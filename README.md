# Repolex Knowledge Graph of sphinx-doc/alabaster

RDF knowledge graph data for [sphinx-doc/alabaster](https://github.com/sphinx-doc/alabaster), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download sphinx-doc/alabaster
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fba58a43980385019ceb593f88ab8821e17840c0
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── fba58a43980385019ceb593f88ab8821e17840c0.nq.gz
│   └── repolex
│       └── fba58a43980385019ceb593f88ab8821e17840c0
│           └── chunk-001.nq.gz
├── blob
│   ├── 008229961986f50bfca4a497b218cafb20f5dd6d.nq.gz
│   ├── 11e36a7afaed839718f86956287bf8ddf416e62e.nq.gz
│   ├── 19361a71900278f15012e023c2abd03ee74f284b.nq.gz
│   ├── 2a924f1d6a8bc930c5296bdb2d5c2d3e39b04a1c.nq.gz
│   ├── 388c835f5b2bb33179c8c6ec82558fe90aedd316.nq.gz
│   ├── 3b2ce043542db0f238af807aa04d924278b84f81.nq.gz
│   ├── 3bf0bd41b687e679f98c5bb5f277f3246f849704.nq.gz
│   ├── 3ceeaa288552ac5d102af09ee276de8bfa94e15c.nq.gz
│   ├── 401b51bfda4b877bb2fecf8a5d33e8e8f52625e3.nq.gz
│   ├── 429bbc2b80fa1ce9748aab79d51ebc3839558618.nq.gz
│   ├── 4dd5e7258ef78fa51a81783b8e642c750be754bc.nq.gz
│   ├── 604f672954bfb89f8e2f6b03aea1929427a3ba47.nq.gz
│   ├── 67dcf255b1840bb654bc1c97e599289d0ee00c93.nq.gz
│   ├── 9ab09da5d4717bddd9890fd792228cdd613f887b.nq.gz
│   ├── c47d9dc0cdc8e7b73b7274b07ac70e79437455ca.nq.gz
│   ├── ca3fb04b1925b6c4b90b492f47eddef8233fde48.nq.gz
│   ├── df2e486c23386b6ccd21c2bcda6977cc9577ba22.nq.gz
│   ├── e4f4a0d333b87cf4a7de2e02fdd338ff5cdff035.nq.gz
│   ├── e6b4848e30d6e2a1dff418463142c806e0acd8b0.nq.gz
│   ├── f3f2708caeb210868a2cf0acb414c322e3f16868.nq.gz
│   ├── f58fe278cc54373f31cc62878526a4d034cc6da9.nq.gz
│   ├── fa2a8447471934537dbb6c9fcabaa0b472f7eb06.nq.gz
│   └── fb472e25c37713ff03cc7667ce2e51c3fcdfda14.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── fba58a43980385019ceb593f88ab8821e17840c0.nq.gz
├── filetree
│   └── fba58a43980385019ceb593f88ab8821e17840c0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 33 files
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

## Source repository

[sphinx-doc/alabaster](https://github.com/sphinx-doc/alabaster)

---
*Parsed on 2026-04-09 by [repolex](https://repolex.ai)*
