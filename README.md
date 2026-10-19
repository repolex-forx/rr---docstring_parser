# Repolex Knowledge Graph of rr-/docstring_parser

RDF knowledge graph data for [rr-/docstring_parser](https://github.com/rr-/docstring_parser), parsed by [repolex](https://repolex.ai).

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
rlex download rr-/docstring_parser
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8347d8fb347bd66e4bf5711d3df586357166944a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8347d8fb347bd66e4bf5711d3df586357166944a
│           └── chunk-001.nq.gz
├── blob
│   ├── 00bc2f985f35805c3bf10766bb4f80ff0d0a3ee5.nq.gz
│   ├── 0118a13f8f619e82cfee85ace835603093a83bb4.nq.gz
│   ├── 0dcba3de6dedec2381ed22ef483e4d6c1a9eeab4.nq.gz
│   ├── 1242d43277017748bbbf3d0a104ec4cf78245822.nq.gz
│   ├── 164665e94d8456d16cb55bbf24dd23cb0978b9c2.nq.gz
│   ├── 19ba3d883e880ec8aedee3eaa4cf2f79fc811e1d.nq.gz
│   ├── 20cf13a1015b15f25a63375c5d3b92610e17ea90.nq.gz
│   ├── 31ad746f7bd08105cc73d20b4d81a463d4523fb6.nq.gz
│   ├── 580c282faea2eace3035c33186fbcd40bd1af9af.nq.gz
│   ├── 5f3532a47526478e8511301871f79fadd779b3b9.nq.gz
│   ├── 772cf2f216dfc6474be4fe5e869b3800ad2fcf99.nq.gz
│   ├── 7965b681376eb82c9f67ca105376dfda0c5b1797.nq.gz
│   ├── 7f6a25cc77773ca4b0744552b442234e2dbdccfc.nq.gz
│   ├── 7fd9cb65ab408af51e2d5e8ce097f6efeb22a7b2.nq.gz
│   ├── 880e37864d59e460e52e5174a6d371c81ea54617.nq.gz
│   ├── 9a945dd6325256535ebacab573433133528bd390.nq.gz
│   ├── a87f58f42c0501bfc2f257720dad6543d7722de0.nq.gz
│   ├── ade85d44b950da9b80b3937e7238b6c5b856e0ae.nq.gz
│   ├── c5be2f5728d40522b23a02a72b1db8ce0da82cb4.nq.gz
│   ├── c769a1f04f5bbb32785dfe6688583effc7f9643d.nq.gz
│   ├── d40d64c484457ff6a9024e00feea4ec2d51b1d6d.nq.gz
│   ├── d5e64994e5397a9b9c12d232768ea02d6091389c.nq.gz
│   ├── d7dfe08ae9d4ce45d02f1e723db5ade79bc70958.nq.gz
│   ├── d80ca29fba2334cb3978686f55037900aeeb19a3.nq.gz
│   ├── de84a85d11747bb90d0650f041292d2d1f099e92.nq.gz
│   ├── e624976acd118ecf0338df744141ffc1ad34dbd6.nq.gz
│   ├── f503a0591a9692f74c715dd9302f7f8ec6aa704b.nq.gz
│   └── f75411dcf7bbeb12daaf9eebc2b9266f3d190ff6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8347d8fb347bd66e4bf5711d3df586357166944a.nq.gz
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

[rr-/docstring_parser](https://github.com/rr-/docstring_parser)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
