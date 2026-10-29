# Architecture Decisions (ADR log)

Terse record of decisions/rulings so features don't relitigate them and agents don't "fix" intentional designs.
Owned by knowledge-keeper. Each: decision → why → source.

---

### D-001 · Same pattern as onedroid-docs
Markdown in `content/`, one-dependency build, markdown twins for agents, no client JS, Vercel git-connected
(`main` → Production). — Michal asked for the docs "set up like" onedroid-docs. _Source: PWW Slack C0CCD6PSQ7R
thread 1793190795.961219, 2026-10-28._

### D-002 · The GitBook protocol docs were ported verbatim, at their old URL paths
`content/3a-protocol/**` mirrors `docs.3adao.org/3a-protocol/**`. Wording was not changed, only GitBook syntax.
— Cutting `docs.3adao.org` over without them would have deleted the protocol docs, audits and contract addresses,
and broken every inbound link. Content problems are logged (F-001…F-005), not silently fixed. _Source: port of
2026-10-28._

### D-003 · Swap pages follow the swap's production code, not its notes
`content/swap/**` was written from `3A-DAO/3adao-ops-swap` at `7de586d` (prod, 2026-10-22). Where the notes and
the code disagreed (EXPIRED wording, send window, withdraw, order cap, rate limit), the code won. Re-check the
pages when the swap ships a user-visible change. _Source: 2026-10-28 docs build._

### D-004 · Repo starts private; `REPO_PUBLIC=false` hides GitHub links
Until 3A DAO decides to open the repo, the footer carries no source/edit links (they would 404). _Source:
`build.mjs` `REPO_PUBLIC`._

---
_Add new decisions above this line. One decision, the why, and a source each._
