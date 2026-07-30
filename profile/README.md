# Palimpsest

> *Nothing is ever truly erased.*

**Palimpsest** is an open-source investigative research engine. It combines persistent memory, unified search across communication channels, platform APIs, web research, and LLM synthesis to build dossiers from fragments.

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

Seven repositories, three layers:

### Search pipeline
**unified-history-mcp** searches across every domain — sessions, transcripts, notifications, and web archives — in a single query. **fst-indexer** (Rust) builds the fast full-text indexes underneath. **web-archive-mcp** captures every web fetch and search result permanently, feeding into the same pipeline.

### Execution
**shell-sandbox-mcp** provides safe command execution via pledge()+unveil() with a vendored busybox — no network, no filesystem escape, no dangerous applets.

### Knowledge
**graph-gardener** maintains the persistent memory graph. **vibe-summarizer** generates AI summaries for sessions and transcripts. **palimpsest** ties it all together as the research engine.

| Repo | Layer | Role |
|---|---|---|
| [unified-history-mcp](https://github.com/palimpsest-labs/unified-history-mcp) | Search | Cross-domain full-text search |
| [fst-indexer](https://github.com/palimpsest-labs/fst-indexer) | Search | Fast full-text indexer (Rust) |
| [web-archive-mcp](https://github.com/palimpsest-labs/web-archive-mcp) | Search | Persistent web fetch/search archiving |
| [shell-sandbox-mcp](https://github.com/palimpsest-labs/shell-sandbox-mcp) | Execution | Safe shell commands via pledge()+unveil() |
| [graph-gardener](https://github.com/palimpsest-labs/graph-gardener) | Knowledge | Memory graph maintenance |
| [vibe-summarizer](https://github.com/palimpsest-labs/vibe-summarizer) | Knowledge | Session/transcript summarization |
| [palimpsest](https://github.com/palimpsest-labs/palimpsest) | Core | Research engine — orchestrates all of the above |

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

Seven repos, all functional, actively developed. The foundation is built — integration is next.

[palimpsest-labs](https://github.com/palimpsest-labs)
