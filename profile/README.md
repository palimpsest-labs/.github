# Palimpsest

> *Nothing is ever truly erased.*

Open-source infrastructure for investigative research. A toolkit that gives journalists and researchers the same persistent intelligence capabilities that institutions have had for decades.

---

## The metaphor

A palimpsest is a manuscript where the original text has been scraped away and overwritten — but the ghost of the first layer remains, recoverable to those who know how to look.

The toolkit works the same way. It searches what's visible, reaches deeper, and preserves what it finds — so nothing fades just because time passed or a page was deleted.

---

## The toolkit

Seven repositories, one integrated pipeline:

### Core

| Repo | Description |
|---|---|
| **[palimpsest](https://github.com/palimpsest-labs/palimpsest)** | Research engine — local-first, source-tracked, methodology-enforced |

### Search & Memory

| Repo | Description |
|---|---|
| **[unified-history-mcp](https://github.com/palimpsest-labs/unified-history-mcp)** | Cross-domain full-text search across sessions, transcripts, notifications, and web archives |
| **[fst-indexer](https://github.com/palimpsest-labs/fst-indexer)** | Blazing-fast FST full-text search indexer (Rust) — the search engine underneath it all |
| **[graph-gardener](https://github.com/palimpsest-labs/graph-gardener)** | LLM-powered knowledge graph maintenance — cleans, enriches, and deduplicates |

### Archiving & Execution

| Repo | Description |
|---|---|
| **[web-archive-mcp](https://github.com/palimpsest-labs/web-archive-mcp)** | Persistent web fetch/search archiving — every result saved and indexed forever |
| **[shell-sandbox-mcp](https://github.com/palimpsest-labs/shell-sandbox-mcp)** | Safe shell command execution via pledge()+unveil() — vendored busybox, cosmo-compiled sandbox |

### Utilities

| Repo | Description |
|---|---|
| **[vibe-summarizer](https://github.com/palimpsest-labs/vibe-summarizer)** | LLM-powered session and transcript summarizer — provider-agnostic |

---

## How they connect

```
shell-sandbox-mcp ──► pledge()+unveil() ──► busybox applets
web-archive-mcp   ──► web_fetch/search   ──► JSONL archive
                          │                      │
                          ▼                      ▼
                    fst-indexer ◄──────── unified-history-mcp
                          │                      │
                          ▼                      ▼
                    graph-gardener          search across all
                          │                 domains at once
                          ▼
                    memory graph
```

---

## Design principles

- **Local-first** — all data stored locally; sensitive investigations never touch the cloud
- **Methodology-enforced** — source provenance, confidence grading, correction logging
- **Self-auditing** — false-positive correction loops, transparent methodology
- **Open source** — no institutional gatekeepers, no licenses, no clearance required
- **Compounding** — the system gets more valuable the longer you use it

---

## Status

Seven repos, all functional, actively developed. The foundation is built. Now we integrate.
