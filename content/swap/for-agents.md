---
title: For AI agents and developers
nav: For agents
description: The machine-readable token list and the read-only MCP server at swap.3adao.org - what each returns, how to call it, and what it cannot do.
section: Swap
order: 21
---

The swap page publishes two machine-readable endpoints for agents, wallets and developers. Both are public, anonymous and read-only. Neither can trade, sign or move funds, and neither gives advice.

## Token list

`https://swap.3adao.org/tokenlist.json` is a list in the Uniswap token-lists format. It holds every OPS token that has a live pool on the swap page, with its name, symbol, checksummed address, decimals and chain id. All of them are on Arbitrum One (chain id 42161).

- The list is built from the live pools feed, so a token is added when its pool gets liquidity and removed when its pool is drained.
- Its `version` field is fixed at 1.0.0 and means nothing. Refresh by `timestamp`, not by `version`.

```bash
curl -s https://swap.3adao.org/tokenlist.json
```

## MCP server

`POST https://swap.3adao.org/api/mcp` is a read-only MCP server (Streamable HTTP, JSON-RPC 2.0). It has two tools.

| Tool | Input | What it returns |
| --- | --- | --- |
| `list_tokens` | none | Every OPS token with a live Uniswap v3 pool on the swap page: symbol, name, address, chain and pool key. |
| `get_token_facts` | `symbol`, for example `OPSBTC` | For one token: the Optima app price, the strategy NAV, the pool price, pool depth and fee tier. Each figure has its own time and a stale flag. It also returns the two ways to trade the token. |

Two prices, two meanings. The **Optima app price** (`app_price`) is the price per token set in the Optima app, where KYC-verified users can buy and redeem. The **strategy NAV** (`strategy_nav`) is the total net asset value of the strategy behind the token, with its name and the token's circulating supply. The **pool price** is what the Uniswap pool on Arbitrum pays now. The pool price is not guaranteed to equal the Optima app price.

List the tools:

```bash
curl -s -X POST https://swap.3adao.org/api/mcp \
  -H "content-type: application/json" \
  -H "accept: application/json, text/event-stream" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

Get the facts for one token:

```bash
curl -s -X POST https://swap.3adao.org/api/mcp \
  -H "content-type: application/json" \
  -H "accept: application/json, text/event-stream" \
  -d '{"jsonrpc":"2.0","id":2,"method":"tools/call","params":{"name":"get_token_facts","arguments":{"symbol":"OPSBTC"}}}'
```

## Read the freshness fields

A successful answer does not mean the data is fresh. Every figure carries the time it was measured and a `stale` flag, with the staleness budget in seconds. Check them before you use a number. If a figure is stale, say so or wait. Do not present it as current.

## More

- The swap page's own description for agents, with the data API behind the page: [swap.3adao.org/llms.txt](https://swap.3adao.org/llms.txt)
- What each token is and which way it moves: [What the OPS swap is](/swap/what-is-the-swap)
- The risks of buying on the swap: [Risks and fees](/swap/risks-and-fees)
