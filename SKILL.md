---
name: antalpha-ai-setup
description: >
  Install and configure the Antalpha Skills MCP server for Web3 trading, smart money tracking, prediction markets, and DeFi analytics. Provides 60+ tools for DEX swaps, smart money signals, Polymarket copy trading, Hyperliquid perpetuals, DeFi discovery, and settlement prediction. Use when the user wants to set up AntAlpha Skills MCP, connect to on-chain data, trade DEX, track whale wallets, or install Web3 analytics tools.
version: 1.0.0
author: antalpha
---

# AntAlpha Skills MCP Server Setup

Connect your AI agent to Antalpha's Web3 unified gateway — 60+ tools covering DEX swaps, smart money signals, Polymarket prediction markets, Hyperliquid perpetual trading, DeFi investment discovery, and EVM/BTC settlement intelligence.

## Prerequisites

- An MCP-compatible client (Claude Code, Claude Desktop, Cursor, Windsurf, etc.)

## Step 1 — Add the MCP Server

**Claude.ai (web):** This cannot be done programmatically. Instruct the user to:

1. Go to Customize → Connectors → Plus button → Add custom connector
2. Name: `AntAlpha Skills`
3. URL: `https://mcp-skills.ai.antalpha.com/mcp`
4. Click Add

**Claude Code** (run in terminal):

```bash
claude mcp add antalpha --transport http https://mcp-skills.ai.antalpha.com/mcp
```

**Codex** (run in terminal):

```bash
codex mcp add antalpha --url https://mcp-skills.ai.antalpha.com/mcp
```

**Claude Desktop / Cursor / Windsurf** (add to MCP config file):

```json
{
  "mcpServers": {
    "antalpha": {
      "url": "https://mcp-skills.ai.antalpha.com/mcp"
    }
  }
}
```

**Gemini CLI** (add to MCP config file):

```json
{
  "mcpServers": {
    "antalpha": {
      "httpUrl": "https://mcp-skills.ai.antalpha.com/mcp"
    }
  }
}
```

**OpenCode** (add to MCP config file):

```json
{
  "mcp": {
    "antalpha": {
      "type": "remote",
      "url": "https://mcp-skills.ai.antalpha.com/mcp"
    }
  }
}
```

**OpenClaw and other stdio-only agents** (uses `mcp-remote` as a bridge):

```json
{
  "mcp": {
    "servers": {
      "antalpha": {
        "command": "npx",
        "args": ["-y", "mcp-remote", "https://mcp-skills.ai.antalpha.com/mcp"]
      }
    }
  }
}
```

## Step 2 — Register Your Agent

After adding the server, register your agent to receive an API key:

1. Ask your agent to call the `antalpha-register` tool
2. It will return an `agent_id` (UUID) and a one-time `api_key`
3. **Save the `api_key`** — it is shown only once

When API key authentication is enabled on the server, include the `api_key` in the `x-antalpha-agent-api-key` HTTP header on all subsequent requests. No OAuth flows, no login pages — just a single key to persist.

If your agent supports MCP headers, configure the `x-antalpha-agent-api-key` header with the returned `api_key`.

## Step 3 — Verify

Ask your agent:

> "Ping the server to verify the connection."

If it calls `test-ping` and returns `{ "ok": true }`, you're connected.

## Step 4 — Get Your First Result

Try one of these prompts:

| What to Say | Tools Used |
|-------------|------------|
| "What's the current quote for 1 ETH to USDC on Ethereum?" | `swap-quote` |
| "Show me the latest high-confidence smart money signals" | `smart-money-signal` |
| "What are the hottest crypto markets on Polymarket right now?" | `poly-trending` |
| "Show me my Hyperliquid positions at 0x..." | `hl-positions` |
| "Discover DeFi opportunities with low risk and APY above 5%" | `investor_discover` |
| "What's the gas situation on Arbitrum?" | `settlement-gas-prediction` |
| "Show all token balances for 0x... across every chain" | `multi-source-token-list` |

## Available Tools (60+)

| Tool | Description |
|------|-------------|
| `antalpha-register` | Register an agent to get agent_id and api_key |
| `test-ping` | Verify server connectivity |
| `multi-source-token-list` | Aggregate token balances across all EVM chains |
| `swap-quote` | Real-time DEX swap quote via 0x |
| `swap-create-page` | Firm 0x quote + cyberpunk swap page HTML |
| `swap-full` | One-shot: quote + swap page + tx data |
| `swap-tokens` | List supported tokens |
| `swap-gas` | Indicative gas price from 0x probe |
| `smart-swap-create` | Create 1inch Fusion Dutch auction order + signing page |
| `smart-swap-list` | List Smart Swap orders for a wallet |
| `smart-swap-status` | Get order status by hash |
| `smart-swap-cancel` | Check Fusion order cancellation status |
| `smart-money-signal` | Trading signals from smart money wallets |
| `smart-money-watch` | Recent activity for a specific wallet |
| `smart-money-list` | List all monitored wallets (public + private) |
| `smart-money-custom` | Add/remove private watchlist addresses |
| `smart-money-scan` | On-demand scan of private watchlist |
| `investor_discover` | Discover DeFi investment opportunities |
| `investor_analyze` | Deep analysis of a DeFi product |
| `investor_compare` | Compare multiple DeFi products |
| `investor_feedback` | Submit feedback on a recommendation |
| `investor_confirm_intent` | Confirm user investment intent |
| `investor_get_stored_intent` | Retrieve stored investment intent |
| `poly-master-traders` | Discover top Polymarket traders |
| `poly-master-follow` | Follow/unfollow a trader for copy trading |
| `poly-master-status` | Copy-trading status and risk config |
| `poly-master-risk` | View/update risk management params |
| `poly-master-pnl` | Copy-trading PnL report |
| `poly-master-orders` | List copy-trading orders |
| `poly-trending` | Trending Polymarket markets by 24h volume |
| `poly-new` | Recently created Polymarket markets |
| `poly-market-info` | Detailed info for a specific market |
| `poly-positions` | Current Polymarket positions for a wallet |
| `poly-history` | Recent trade activity for a wallet |
| `poly-buy` | Buy outcome tokens via EIP-712 signing page |
| `poly-sell` | Sell outcome tokens via EIP-712 signing page |
| `poly-confirm` | Check poly-buy/sell order status |
| `hl-price` | Get asset prices (Top 10 if no coin) |
| `hl-account` | Hyperliquid account summary |
| `hl-book` | L2 order book depth |
| `hl-orders` | Open orders |
| `hl-positions` | Open perpetual positions |
| `hl-funding` | Funding rates sorted by magnitude |
| `hl-balance-check` | Pre-check sufficient balance |
| `hl-limit-order` | Place a limit order |
| `hl-market-order` | Place a market order |
| `hl-close` | Close position at market |
| `hl-cancel` | Cancel an order |
| `hl-leverage` | Set leverage |
| `hl-tp-sl` | Place take-profit / stop-loss order |
| `hl-modify-order` | Modify an existing order |
| `settlement-gas-prediction` | EVM gas tier estimates |
| `settlement-predict-time` | Predict tx confirmation time |
| `settlement-optimal-window` | Best time to send a tx |
| `settlement-pending-pool` | Sandwich attack risk analysis |
| `settlement-track-tx` | Track EVM tx status |
| `settlement-verify-contract` | Check contract verification on explorer |
| `settlement-token-info` | ERC-20 token metadata on-chain |
| `settlement-btc-fee` | BTC mempool fee tiers |
| `settlement-btc-settlement` | BTC confirmation time prediction |
| `settlement-track-btc-tx` | Track BTC tx status |

## Troubleshooting

- **"Agent validation failed"**: Call `antalpha-register` first and persist the returned `agent_id` and `api_key`. When the server has `AGENT_API_KEY_AUTH_ENABLED=true`, send the `api_key` on each MCP HTTP request using the `x-antalpha-agent-api-key` header.
- **No tools available**: Verify the MCP server URL is exactly `https://mcp-skills.ai.antalpha.com/mcp` (note the `/mcp` path).
- **Rate limited**: The tool call frequency is limited per IP. Wait a moment and retry, or contact the service provider to adjust limits.
- **Smart Swap not filling**: Smart Swap currently only supports `chain_id=1` (Ethereum mainnet) with `engine=1inch`. The order uses a Dutch auction mechanism — it may take 3–10 minutes to fill or auto-expire.
- **Hyperliquid write tools require a private key**: Tools like `hl-limit-order` require your `agent_key` (Hyperliquid private key) and `owner` address in the input. The key is used only for signing the current request and is never stored server-side.
- **Polymarket trades use signing pages**: `poly-buy` and `poly-sell` generate EIP-712 signing pages. Open the returned `preview_url` in your wallet browser to sign — your private key never leaves your wallet.
