# Data Flow — the data-transform view of THIS repo

Companion to `SERVICE-MAP.md`. There is one datum here, a page of documentation, and one interesting question
about it: **which copy is true.**

## Data nodes
| Node | Shape / schema | Origin | Authority | Class |
|---|---|---|---|---|
| `page source` | markdown + `---` frontmatter (`title`, `description` required; `section`, `order`, `nav` optional) | a human or agent editing `content/**/*.md` | **`content/` in this repo, the only one** | public |
| `dist/ HTML` | rendered page, nav + canonical + og tags | `build.mjs` `page()` | `content/` (derived) | public |
| `dist/<slug>.md` | **byte-identical copy of `page source`** | `build.mjs` emit (`p.raw`) | `content/` (derived) | public |
| `llms.txt`, `sitemap.xml`, `robots.txt` | generated indexes | `build.mjs` emit | `content/` (derived) | public |
| `docs.3adao.org` response | what a reader sees | Vercel deploy of `dist/`, plus `middleware.js` on the agent path | `content/` (derived, may be stale) | public |
| swap behaviour described in `content/swap/` | prose about a live money flow | `3A-DAO/3adao-ops-swap` `main` | **the swap code and the live site**, never this repo | public |

## Transform graph
```
page source (content/**/*.md)
   │  parse frontmatter (pure; THROWS on missing title/description)
   │  marked.parse + template (pure)                 ──►  dist/<slug>/index.html
   │  passthrough of p.raw (pure, byte-identical)    ──►  dist/<slug>.md
   │  index generation (pure)                        ──►  llms.txt · sitemap.xml · robots.txt
   ▼
git merge to main ──► Vercel build + deploy (effect: idempotent by commit; undo = redeploy a prior commit)
                  ──► middleware.js rewrite on agent UA (pure per-request)
```

## Validation rules
| Rule | Locus | Action on violation | Enforced at |
|---|---|---|---|
| every page has `title` and `description` | LOCAL | build fails | `build.mjs` |
| images are PNG under `content/img/`, resolve, carry alt text | LOCAL | build fails | `build.mjs` |
| `dist/` matches a fresh build | GLOBAL | regenerate, never edit `dist/` | `npm run check` |
| a published page disagrees with the markdown | GLOBAL | the markdown is right; redeploy | `AGENTS.md` |
| a swap page disagrees with the swap code | GLOBAL | **the code is right; fix the page** | reviewer, not mechanical |
| no operator data (P&L, treasury/Safe/operator wallets, funding, per-user data) | GLOBAL | remove before merge | reviewer, not mechanical |

⚠️ The last two rules have no mechanical enforcer. A green `npm run check` means `dist/` is current, never that the
docs are right.
