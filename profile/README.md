# Palimpsest

> *Nothing is ever truly erased.*

**Palimpsest** is an open-source investigative research engine. It combines persistent memory, unified search across communication channels, platform APIs, web research, and LLM synthesis to build dossiers from fragments.

---

## The metaphor

A palimpsest is a manuscript where the original text has been scraped away and overwritten — but the ghost of the first layer remains, recoverable to those who know how to look.

The tool works the same way. It searches what's visible, then reaches deeper: deleted pages in the Wayback Machine, buried conversations in chat logs, forgotten connections in commit histories. Every finding is a layer. The truth is in the traces.

---

## What it does

- **Unified search** — query across chat logs, meeting transcripts, session history, and command history in a single operation
- **Platform intelligence** — GitHub, GitLab, Jira/Confluence, Wayback Machine, public social profiles
- **Web research** — web search with source attribution, domain WHOIS, company registries, Wayback reconstruction
- **Persistent memory** — knowledge graph across sessions (people, events, findings, timelines, sources) with automatic relation mapping
- **LLM synthesis** — connects dots across data sources, identifies patterns, highlights gaps, suggests next lines of inquiry
- **Output** — structured dossiers, network maps, timelines, source indices with provenance and confidence ratings

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

Palimpsest is in early design. We're building the foundation.

[palimpsest-labs](https://github.com/palimpsest-labs)
