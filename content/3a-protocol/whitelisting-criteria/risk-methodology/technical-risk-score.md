---
title: Technical Risk Score
description: Scoring table for the technical risk category: code, documentation, testing and auditing.
section: Protocol: Whitelisting
order: 138
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

| Category | Description | Max Points |
| --- | --- | --- |
| Code (45%) | Executing code has the addresses readily available | 10 |
|  | No. of days since the code was in production with no issues (>365 gets max; &lt;90 days is 0 ) | Linear distribution maxed at 35 |
| Documentation (35%) | Whitepaper (Y/N) | 10 |
|  | Basic software functions documented (Y/N | 10 |
|  | Full documentation for all software functions | 10 |
|  | Pause Control documentation | 5 |
| Testing (10%) | Full test suite | 5 |
|  | Script and instructions to run the tests? (Y/N) | 3 |
|  | Stress testing environment | 2 |
| Auditing (10%) | Bug bounty | 10 |
