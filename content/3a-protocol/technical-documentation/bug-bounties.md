---
title: Bug Bounties
description: Incentives for community members to review the protocol and submit issues
section: Protocol: Technical
order: 133
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

### Scope <a href="#scope" id="scope"></a>

The bounty program covers exclusively the smart-contract portion of the protocol. The issues should be submitted as tickets on [Discord](https://discord.gg/7PcFq4MBkF) ​

### Rewards <a href="#rewards" id="rewards"></a>

The rewards are different for each severity level of the bug:

* minor: 5,000 A3A - 3 or 4 points
* medium: 15,000 A3A - 5 or 6 points
* major: 500,000 A3A - 7 or 8 points
* critical: 5,000,000 A3A - 9 or 10 points

The severity is determined by two factors:

1. Likelihood - the certainty with which an issue will arise
2. Impact - should the issue arise, how devastating it would be

#### Likelihood <a href="#likelihood" id="likelihood"></a>

The more likely an issue is to occur, the more points it is given. From a maximum of 5 points for a dead certain occurrence to 1 for an issue that only arises in edge cases.

1. Very unlikely, edge cases only. Probably never occurs.
2. Low probability, edge cases that have a good chance of occurring.
3. Potential for a security incident in the long run. We have time, but it needs fixing.
4. High probability of a security incident. Needs to be fixed right away.
5. Dead certain and it could happen tomorrow. The protocol needs to be paused.

#### Impact <a href="#impact" id="impact"></a>

In the same spirit, the higher the impact, the more points an issue gets. From 5 points for a catastrophic issue to 1 point for an annoying bug.

1. Is annoying but has an easy workaround
2. May cause loss of functionality but not of funds
3. May cause loss of funds in some cases
4. Allows an attacker to gain access to a large portion of the value locked
5. Allows an attacker to gain access to all of the value locked unless the protocol is paused
