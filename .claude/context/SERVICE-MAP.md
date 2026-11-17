# Service Map (compressed)

`3A-DAO/3adao-docs`: the markdown source of truth for **https://docs.3adao.org**. The repo is authoritative; the
site is a build artefact. There are no services here: one build script, one edge function, one dependency.
Verify against code before acting; flag drift to knowledge-keeper.

⚠️ **`AGENTS.md` at the repo root is authoritative for HOUSE RULES** (verify before you write, no operator data,
never advise clicking through a wallet warning). This store describes STRUCTURE only.

## Components
| Component | Lang | Role | In → Out |
|---|---|---|---|
| `build.mjs` | Node ESM | The whole build. Walks `content/` recursively, parses frontmatter, renders HTML + the byte-identical markdown twin, generates nav / `llms.txt` / `sitemap.xml` / `robots.txt` | `content/**/*.md` → `dist/` |
| `build.mjs --check` | Node ESM | Staleness check: exits 1 if `dist/` would differ from a fresh build. `npm run check` | `content/` + `dist/` → exit 0/1 |
| `middleware.js` | Vercel Edge | Serves the **markdown source** to AI-agent user-agents at the canonical URL | request → `x-middleware-rewrite` to `<path>.md` |
| `vercel.json` | config | Build command, `cleanUrls`, security headers, `text/markdown` on `*.md`, redirects for old GitBook URLs | — |
| `content/**/*.md` | markdown | The only place to change what the site says. `content/swap/` = the swap; `content/3a-protocol/` = the borrowing protocol, ported from GitBook with its URL paths | — |

## Cross-component contracts that silently break if drifted
- **Frontmatter `title` + `description` are REQUIRED**; the build throws without them.
- **Images**: PNG only, under `content/img/`, referenced as `/img/...`, with alt text, or the build throws.
- **Downloads**: PDF only, under `content/files/<page>/`, linked as `/files/...`; a link to a missing file throws.
- **`dist/` is generated and gitignored.** Vercel builds it from `content/` on every deploy.
- **The markdown twin is the SOURCE, byte for byte** (`files.set(..., p.raw)`).
- **`middleware.js` cannot be a `vercel.json` rewrite**: Vercel evaluates rewrites only after the filesystem
  check, so a rewrite on a path that resolves to a file never fires.
- **`/3a-protocol/...` paths are the old GitBook URLs.** They are linked from the borrowing-protocol README, audits
  and third parties. Renaming a file under `content/3a-protocol/` breaks an inbound link unless `vercel.json` gets a
  redirect.
- **`REPO_PUBLIC`** in `build.mjs` (true since 2026-10-29, D-005) adds source, edit and issue links to every page.
  Set it to false if the repo goes private again, or the links 404.

## Infra & cross-cutting
- **Host**: Vercel team `optima-fi`, project `3adao-docs`, git-connected. `main` → Production; other branches → Preview.
- **Domain**: `docs.3adao.org` (Cloudflare DNS, zone `3adao.org`). Before 2026-10-28 it pointed at GitBook.
- **Dependencies**: exactly one, `marked ^15.0.0`.
- **No client-side JavaScript.**
- **Documented subjects**: the OPS swap at swap.3adao.org (code: `3A-DAO/3adao-ops-swap`, read its
  `.claude/context/` store), and the 3A borrowing protocol (code: `3A-DAO/3a-borrowing-protocol`).

---
_Add components above this line. Cite a `file:line` or ruling for every claim; verify against code before acting._
