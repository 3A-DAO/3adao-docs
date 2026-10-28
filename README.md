# 3adao-docs

Markdown source of truth for **[docs.3adao.org](https://docs.3adao.org)**.

## What these docs are

- **The OPS swap** at [swap.3adao.org](https://swap.3adao.org): what OPSBTC and OPSSOL are, how to buy them with
  USDC on Arbitrum or with a token from another EVM chain, what each screen means, and what to do when something
  goes wrong.
- **The 3A borrowing protocol**: EURO3, vaults, the Stability Pool, liquidations, the A3A token, contracts and
  audits. These pages were moved here from the old GitBook site and keep its URLs (`/3a-protocol/...`).
  `vercel.json` redirects `/3a-protocol` to its welcome page, and the unprefixed GitBook paths
  (`/protocol-documentation/...` and the other top-level sections) to their `/3a-protocol/...` page.

## How the repo works

Edit a file in `content/`, open a pull request, and once it is merged to `main` Vercel rebuilds the site. There is
exactly one copy of every sentence: the repo. The site is a build artefact.

## Layout

```
content/**/*.md  the docs. frontmatter: title, description, nav, section, order
content/img/**   screenshots, PNG only
content/files/** downloads (audit reports, brand sheets), PDF only, linked as /files/<page>/<name>.pdf
build.mjs        markdown -> dist/. one dependency (marked)
middleware.js    serves the markdown source to AI agents at the canonical URL
vercel.json      build config, headers, redirects
```

## Local

```bash
npm install
npm run build      # -> dist/
npm run check      # exit 1 if dist/ is stale
```

## Adding a page

Create `content/<slug>.md` (folders are allowed: `content/3a-protocol/lending.md` is served at
`/3a-protocol/lending`) with frontmatter:

```markdown
---
title: Buy with USDC on Arbitrum
nav: Buy on Arbitrum
description: One sentence. It is the page's meta description and its llms.txt line.
section: Swap
order: 12
---
```

`title` and `description` are required; the build fails without them. `section` groups the nav, `order` sorts it,
`nav` overrides the sidebar label. Sections appear in the order of their first page, so keep a page inside its
section's range: `Start here` 1–9, `Swap` 10–39, `3A Protocol` 100 and up.

Navigation, `llms.txt`, `sitemap.xml` and `robots.txt` are generated from the content.

## Agent-readable by construction

Every page is served as markdown at `<path>.md`, and to AI-agent user-agents (or `Accept: text/markdown`) at the
canonical URL. The markdown served is the source file, byte for byte.

## Why the site has almost no dependencies

`marked` is the only one. Docs for a DeFi product are a security surface: a compromised build step would serve
wrong addresses or links to every reader. The build is a single file you can read in a sitting, and there is no
client-side JavaScript.
