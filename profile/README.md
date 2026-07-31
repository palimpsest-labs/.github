# Palimpsest

> *Ghost in the pages.*

**Palimpsest** is an open-source intelligence fusion tool for investigative research. It gives journalists and researchers the same persistent intelligence capabilities — cross-domain search, knowledge graphs, web archiving, secure execution — that institutions have had for decades. Local-first, source-tracked, methodology-enforced.

---

## The metaphor

A palimpsest is a manuscript where the original text has been scraped away and overwritten — but the ghost of the first layer remains, recoverable to those who know how to look.

The tool works the same way. It searches what's visible, then reaches deeper: deleted pages in the Wayback Machine, buried conversations in chat logs, forgotten connections in commit histories. Every finding is a layer. The truth is in the traces.

---

## What it does

- **Unified search** — query across chat logs, meeting transcripts, session history, command history, and web archives in a single operation
- **Platform intelligence** — GitHub, GitLab, Jira/Confluence, Wayback Machine, public social profiles
- **Web research** — web search with source attribution, domain WHOIS, company registries, Wayback reconstruction
- **Persistent memory** — knowledge graph across sessions (people, events, findings, timelines, sources) with automatic relation mapping
- **Safe execution** — sandboxed shell commands via pledge()+unveil() with vendored busybox
- **LLM synthesis** — connects dots across data sources, identifies patterns, highlights gaps, suggests next lines of inquiry
- **Output** — structured dossiers, network maps, timelines, source indices with provenance and confidence ratings

---

## The toolkit

Twelve repositories, six layers:

### Core
**palimpsest** is the research engine that orchestrates the whole stack — the case directory system, methodology gates, evidence capture, and the agent loop.

### Search
**unified-history-mcp** searches across every domain — sessions, transcripts, notifications, and web archives — in a single query. **fst-indexer** (Rust) builds the fast full-text indexes underneath.

### Knowledge
**memory-mcp** is the persistent SQLite-backed knowledge graph — graph traversal, fuzzy search, temporal queries. **memory-stats-mcp** exposes read-only graph stats and discovery. **graph-gardener** maintains the graph — deduplication, enrichment, cleanup. **vibe-summarizer** generates AI summaries for sessions and transcripts.

### Execution
**shell-sandbox-mcp** provides safe command execution via pledge()+unveil() with a vendored busybox — no network, no filesystem escape, no dangerous applets.

### Web & document research (OSINT)
**web-archive-mcp** captures every web fetch and search result permanently. **dns-whois-mcp** resolves DNS and WHOIS registration data. **image-analysis-mcp** runs OCR and extracts EXIF/metadata from images. **pdf-extract-mcp** extracts text and metadata from PDFs — all feeding the same search pipeline.

| Repo | Layer | Role |
|---|---|---|
| [palimpsest](https://github.com/palimpsest-labs/palimpsest) | Core | Research engine — orchestrates all of the above |
| [unified-history-mcp](https://github.com/palimpsest-labs/unified-history-mcp) | Search | Cross-domain full-text search |
| [fst-indexer](https://github.com/palimpsest-labs/fst-indexer) | Search | Fast full-text indexer (Rust) |
| [memory-mcp](https://github.com/palimpsest-labs/memory-mcp) | Knowledge | Persistent SQLite knowledge graph |
| [memory-stats-mcp](https://github.com/palimpsest-labs/memory-stats-mcp) | Knowledge | Read-only graph stats & discovery |
| [graph-gardener](https://github.com/palimpsest-labs/graph-gardener) | Knowledge | Memory graph maintenance |
| [vibe-summarizer](https://github.com/palimpsest-labs/vibe-summarizer) | Knowledge | Session/transcript summarization |
| [shell-sandbox-mcp](https://github.com/palimpsest-labs/shell-sandbox-mcp) | Execution | Safe shell commands via pledge()+unveil() |
| [web-archive-mcp](https://github.com/palimpsest-labs/web-archive-mcp) | OSINT | Persistent web fetch/search archiving |
| [dns-whois-mcp](https://github.com/palimpsest-labs/dns-whois-mcp) | OSINT | DNS lookup & WHOIS registration research |
| [image-analysis-mcp](https://github.com/palimpsest-labs/image-analysis-mcp) | OSINT | OCR & image metadata/EXIF extraction |
| [pdf-extract-mcp](https://github.com/palimpsest-labs/pdf-extract-mcp) | OSINT | PDF text & metadata extraction |

---

## Design principles

- **Non-technical UX** — a journalist types "investigate X" and gets results
- **Local-first** — all data stored locally; sensitive investigations never touch the cloud
- **Offline-capable** — no dependency on external services for core operation
- **Source provenance** — every finding traces back to its origin
- **Confidence grading** — confirmed → circumstantial → speculative
- **Model-agnostic** — works with any LLM provider

---

## Status

Twelve repos, all functional, actively developed. The foundation is built — integration and the mobile companion are next.

[palimpsest-labs](https://github.com/palimpsest-labs)
