---
title: Technical Risk Score
description: Scoring table for the technical risk category: code, documentation, testing and auditing.
section: Protocol: Whitelisting
order: 138
---

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
