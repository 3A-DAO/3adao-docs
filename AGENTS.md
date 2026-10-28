# AGENTS.md

Instructions for coding agents working in this repo. Humans: see [README.md](README.md).

## What this repo is

The markdown source of truth for **https://docs.3adao.org**. The repo is authoritative; the site is a build
artefact. If a published page disagrees with the markdown here, the markdown is right and the site is stale.

## Layout

- `content/**/*.md`: the docs. This is the only place to change what the site says.
- `build.mjs`: markdown → `dist/`. One dependency (`marked`).
- `middleware.js`: serves the markdown source to AI agents at the canonical URL.
- `vercel.json`: build config, headers, and the redirects that keep old GitBook URLs working.
- `dist/`, `node_modules/`: not content. Never edit `dist/` by hand.
- `.claude/`: the agent inner loop (context store, subagents, gates). Start at [CLAUDE.md](CLAUDE.md).

## Making a change

```bash
npm install
npm run build     # regenerate dist/
npm run check     # exits 1 if dist/ is stale
```

Every page needs `title` and `description` in frontmatter; the build fails without them.

## House rules

**Changes reach `main` only through a pull request.** A merge to `main` is a production deploy of
docs.3adao.org, and it is Michal's call.

**Do not document behaviour you have not verified.** The swap pages describe a live site that moves real money.
Every statement about what the swap does must come from its code (`3A-DAO/3adao-ops-swap`, branch `main`) or
from using the live site. A confident wrong page about a money flow is worse than a missing one.

**Never publish operator data.** No P&L, no treasury, Safe or operator wallet addresses, no funding figures, no
per-user data. Contract and pool addresses that are already public on-chain are fine.

**Never tell a reader to click through a wallet security warning.** If a wallet warns, the page says stop.

**Prefer the failure over the happy path.** The pages people need most are the ones for when a buy is stuck,
expired, or left dust behind.

**No client-side JavaScript, and no second copy.** Link instead of copying.

## Where things are published

- Site: https://docs.3adao.org (Vercel team `optima-fi`, project `3adao-docs`, production branch `main`)
- Machine index: https://docs.3adao.org/llms.txt
