# Repolex Knowledge Graph of expressjs/compression

RDF knowledge graph data for [expressjs/compression](https://github.com/expressjs/compression), parsed by [repolex](https://repolex.ai).

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
lexq download expressjs/compression
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 83a0c45fe190f4fcb8b515c18065db9cb9029dd1
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 83a0c45fe190f4fcb8b515c18065db9cb9029dd1.nq.gz
│   └── repolex
│       └── 83a0c45fe190f4fcb8b515c18065db9cb9029dd1
│           └── chunk-001.nq.gz
├── blob
│   ├── 0678bf2a71a289690fa20bc35c09d7654b278236.nq.gz
│   ├── 0b9ac02903721b0b85f41e33740cf3a76f05f942.nq.gz
│   ├── 32637d0ec463035a4e0662308f330f2c38dbdf21.nq.gz
│   ├── 386b7b6946e47bc46f8138791049b4e6a7cef889.nq.gz
│   ├── 62562b74a3b5a79e82ca417b02e0f597d85f5e2f.nq.gz
│   ├── 693056111f4469252e04b7a3019fa65bfa581366.nq.gz
│   ├── 8107def07d1edf214367c97b7cb07cdf396ea3ed.nq.gz
│   ├── 918b82b2c507473f3ba032be4931df15a01c9147.nq.gz
│   ├── 9808c3b2b6602da61eb4afcb4caf33368e3e2bd4.nq.gz
│   ├── 9b328ebc2327495ff2f9ec6f1ad8c208289042a0.nq.gz
│   ├── a6096a49b45192e7c5ac5f0f2bdcb17d0b18d1b1.nq.gz
│   ├── c0638e08280d5f67067c225f0e6f471f90065fcb.nq.gz
│   ├── cf3015fb3b6ee818a7e76aff5854cde130fc5fe0.nq.gz
│   └── df1bd789478aeee37554f514025281f17ab687cc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 83a0c45fe190f4fcb8b515c18065db9cb9029dd1.nq.gz
├── filetree
│   └── 83a0c45fe190f4fcb8b515c18065db9cb9029dd1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 24 files
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

[expressjs/compression](https://github.com/expressjs/compression)

---
*Parsed on 2026-04-14 by [repolex](https://repolex.ai)*
