# Findings Ledger — known bugs & root causes

Append-only memory of confirmed problems so they are **never re-investigated**. Before investigating, search here.
Each entry: symptom → root cause → ref → status. Owned by knowledge-keeper; any agent may propose an entry with evidence.

Format: `STATUS` ∈ OPEN | FIX-PLANNED | FIXED | WONTFIX.

---

### F-001 · Ported protocol pages carry GitBook-era content that is stale · OPEN
- **Symptom**: pages read as if it were 2023–2024: "Coming up in Q1 2024", "At launch…", release schedule through 2026,
  a testnet API page (`api-testnet.3adao.org`, BuildBear RPC), a RedBelly testnet contracts page.
- **Root cause**: ported verbatim from GitBook on 2026-10-28 (D-002); the source was never updated.
- **Refs**: `content/3a-protocol/protocol-documentation/premium-services/vault-optimization-bot.md:3`,
  `whitelisting-criteria/whitelisted-tokens.md:8`, `protocol-documentation/a3a-token.md:20,24`,
  `protocol-documentation/lending/redemptions.md:12`, `user-guide/frequently-asked-questions.md:151,155,189`,
  `technical-documentation/smart-contracts/api.md:26`, `technical-documentation/smart-contracts/redbelly-testnet-contracts.md`.
- **Fix direction**: someone who knows the protocol's current state rewrites or retires each page. Not an agent guess.

### F-002 · Polygon contract table has suspect addresses · OPEN
- **Symptom**: the Stability Pool link text is truncated with a stray `f`; WMATIC/WETH link texts are truncated;
  PriceOrchestrator v1.0.0 links to the Vault Borrow Rate address; the Polygon DAI collateral address equals the Linea
  "Vault Factory Helper" address and the Polygon "USD/EURO" feed equals the Linea "Vault Borrow Rate" address.
- **Root cause**: present in the GitBook source (copy-paste errors); carried over by the verbatim port.
- **Refs**: `content/3a-protocol/technical-documentation/smart-contracts/polygon-mainnet-contracts.md:13,27,32-35`.
- **Fix direction**: check each address on-chain against `3A-DAO/3a-borrowing-protocol` deployments, then correct.
  A wrong contract address on a DeFi docs site is a funds risk: treat as high priority.

### F-003 · Code examples in "Borrowing and Repaying" are wrong · OPEN
- **Symptom**: `healthFactor > 2 ** 1e18`; `euro3.approve(vaultDebt, vaultDebt)` passes an amount where the spender goes.
- **Root cause**: GitBook source.
- **Refs**: `content/3a-protocol/technical-documentation/smart-contracts/interacting-with-contracts/borrowing-and-repaying.md`.
- **Fix direction**: correct against the contract ABI in `3A-DAO/3a-borrowing-protocol`.

### F-004 · Port gaps: PDFs hosted on GitBook, one image skipped · PDFs FIXED, image OPEN
- **Fixed 2026-10-28**: all 8 PDFs (5 audits, the LLC charter certificate, 2 palettes) are now in
  `content/files/<page>/`, served by `build.mjs`, and the links point there. The note below that the charter PDF was
  dropped was wrong: it was linked on `governance/3a-dao.md:19`.
- **Symptom**: the 3A DAO LLC document on `governance/3a-dao` was dropped (no resolvable URL); the 5 audit PDFs and
  2 palette PDFs link to `*.files.gitbook.io` and die if the GitBook space is deleted; the Centurion NFT image
  (>2 MB) is skipped (`community-rewards/centurion.md:7`, HTML comment).
- **Root cause**: `build.mjs` serves PNG only under `content/img/`; there is no home for PDFs.
- **Fix direction**: download the PDFs into the repo with a PDF allowance in `build.mjs` before the GitBook space is
  removed; downscale the Centurion image.

### F-005 · Inconsistent contact links on ported pages · OPEN
- **Symptom**: two different Discord invites (`bug-bounties.md:10`, `governance/forum-discussions.md:8` vs
  `communication/contact-us.md`); neither checked for expiry. "(see Disclaimer)" on `welcome-to-3a.md` points nowhere.
- **Fix direction**: ask 3A DAO for the current official links.

### F-006 · The protocol the ported pages describe was shut down in 2024 · FIXED (notice)
- **Symptom**: GitBook pages read as a live product ("To borrow EURO3, all you need is a wallet…").
- **Root cause**: 3A DAO phased out the lending protocol and EURO3 on Linea and Polygon (no new loans from
  2024-10-01, all vaults closed 2024-11-30), per its own post
  https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8. GitBook was never updated.
- **Fix**: every page under `content/3a-protocol/` opens with an "Archived" blockquote (marker
  `<!-- archive-notice -->`, so a re-port can find it), and `content/index.md` labels the section archived.
  The notice is in the markdown, not the HTML template, so the `.md` twins agents read carry it too.
- **Open**: the same post says the RedBelly testnet app and the DAG bridge continue; the RedBelly testnet page is
  archived along with the rest until someone confirms its state.

---
_Add new confirmed findings above this line. Cite a `file:line` or ruling for every claim._
