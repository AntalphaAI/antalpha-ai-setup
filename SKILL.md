---
name: antalpha-ai-setup
description: Install and configure the Antalpha Skills MCP server. Provides 146+ Web3 tools for DEX swaps, smart money tracking, Polymarket prediction markets, Hyperliquid perpetuals, CEX trading, Bitcoin mining, and DeFi analytics.
version: 2.0.0
author: Antalpha Labs
homepage: https://mcp-skills.ai.antalpha.com
---

# Antalpha Skills MCP Server Setup

## Overview
The Antalpha Skills MCP server provides 146+ Web3 tools for AI agents, including DEX swaps, smart money tracking, Polymarket prediction markets, Hyperliquid perpetuals, CEX trading, Bitcoin mining, and DeFi analytics. This server enables AI agents to interact with various Web3 protocols through a unified Model Context Protocol (MCP) interface.

## Quick Install
```bash
mcporter add https://mcp-skills.ai.antalpha.com/mcp --name antalpha-skills
```

## Prerequisites
- An AI agent capable of using Model Context Protocol (MCP) servers
- Access to the Antalpha Skills MCP server at `https://mcp-skills.ai.antalpha.com/mcp`
- Agent registration with Antalpha (contact team for access)

## Step 1: Add MCP Server
Add the Antalpha Skills server to your MCP-compatible client:

### Claude.ai / Claude Code
1. Go to Settings → Integrations
2. Click "Add Integration"
3. Enter URL: `https://mcp-skills.ai.antalpha.com/mcp`
4. Follow authentication prompts

### Codex
1. Open Codex settings
2. Navigate to "External Services"
3. Add new service with URL: `https://mcp-skills.ai.antalpha.com/mcp`

### Claude Desktop/Cursor/Windsurf
1. Access MCP integrations panel
2. Select "Add New Server"
3. Enter: `https://mcp-skills.ai.antalpha.com/mcp`

### Gemini CLI
1. Configure MCP endpoints
2. Add: `https://mcp-skills.ai.antalpha.com/mcp`

### OpenCode
1. In settings, find "MCP Servers"
2. Add the Antalpha endpoint

### OpenClaw
Edit your OpenClaw configuration to include:
```json
{
  "mcpServers": [
    {
      "name": "antalpha-skills",
      "url": "https://mcp-skills.ai.antalpha.com/mcp",
      "enabled": true
    }
  ]
}
```

Note: For OpenClaw, use the direct HTTP URL rather than the npx mcp-remote command.

## Step 2: Register Your Agent
Contact the Antalpha team to register your AI agent. You'll need to provide:
- Agent name and description
- Intended use case
- Expected request volume
- Contact information for support

Upon registration, you'll receive agent-specific credentials and rate limits.

## Step 3: Verify Installation
Test your installation by running the ping command:

```bash
# If using the test tool directly
test-ping
```

This should return a simple confirmation that your agent can communicate with the Antalpha Skills server.

## Step 4: Get Your First Result
Try one of these example prompts to verify functionality:

| Prompt | Expected Result |
|--------|----------------|
| "Get current BTC and ETH prices" | Returns latest price data for both cryptocurrencies |
| "Check wallet balance for 0x&lt;your_wallet_address&gt;" | Shows token balances for the specified address |
| "Show trending airdrops" | Lists current airdrop opportunities |
| "Get Hyperliquid account info for address" | Retrieves account details from Hyperliquid |

## Available Tools
| Tool | Description |
|------|-------------|
| antalpha-register | Register this agent with Antalpha platform |
| swap-create-page | Generate a DEX swap signing page from an existing quote |
| swap-full | Execute a DEX token swap end-to-end: gets firm quote + generates signing page + hosts it |
| swap-gas | Get a quick gas estimate (Gwei + units) scoped specifically to the current swap |
| swap-quote | Get a DEX swap quote: expected output amount, minimum receive after slippage, gas estimate,… |
| swap-tokens | List all supported DEX tokens: symbol, name, contract address, decimals |
| smart-swap-cancel | Check the cancellation or expiry status of a 1inch Fusion smart swap order |
| smart-swap-create | Create a 1inch Fusion (Dutch auction) MEV-protected swap order |
| smart-swap-list | List all smart swap orders for a wallet: active (in auction), filled, cancelled |
| smart-swap-status | Check current execution status of a smart swap order: auction progress, fill percentage,… |
| smart-money-custom | Manage your smart-money watchlist & settings — add or remove a private wallet (max 5),… |
| smart-money-list | View / list the wallets currently being monitored — the pre-loaded public smart-money… |
| smart-money-pool | View LP (liquidity provider) activity for smart money addresses: pool add/remove events,… |
| smart-money-signal | Get aggregated trading signals from ALL monitored wallets |
| smart-money-watch | View a single wallet's recent on-chain activity |
| poly-buy | Buy outcome tokens on Polymarket |
| poly-confirm | Check Polymarket order status: signing status (pending/signed/expired) and fill status… |
| poly-history | Get recent trade and transfer activity for a Polymarket proxy wallet |
| poly-intel | Polymarket cross-market and cross-wallet analytics (Arkham-backed cache layer) |
| poly-market-info | Get full detail for ONE known Polymarket market: conditionId, outcomes/prices, volume,… |
| poly-master-follow | Follow or unfollow a Polymarket trader |
| poly-master-orders | List copy-trading orders with status filter (pending/filled/cancelled) |
| poly-master-pnl | PnL report for copy-trading: breakdown by daily/weekly/total and by followed trader |
| poly-master-risk | View or update copy-trading risk limits: max position size, daily loss limit, copy ratio… |
| poly-master-search-market | Free-text search across ALL Polymarket prediction markets |
| poly-master-status | Single-call copy-trading dashboard: followed traders, recent orders, current risk config |
| poly-master-strategy-dry-run | Toggle dry-run mode for the strategy engine |
| poly-master-strategy-metrics | Get the strategy engine monitoring dashboard: signal tier distribution (T1/T2/T3), signal… |
| poly-master-strategy-scan | Scan for logical-implication hedge arbitrage signals across Polymarket |
| poly-master-traders | Discover top Polymarket traders ranked by win rate, ROI, volume, active markets |
| poly-new | Get recently created Polymarket markets sorted by creation date |
| poly-order-status | Complete alias of poly-confirm |
| poly-positions | Get current Polymarket positions: outcome tokens held, cost basis, current market value,… |
| poly-sell | Sell outcome tokens on Polymarket |
| poly-trending | Get trending Polymarket prediction markets sorted by 24h volume |
| hyperliquid-account | Get Hyperliquid account summary: balances, positions, open orders |
| hyperliquid-balance-check | Pre-check if account has sufficient balance for a trade |
| hyperliquid-book | Get L2 order book for a Hyperliquid perp asset |
| hyperliquid-cancel | Cancel an open order on Hyperliquid |
| hyperliquid-close | Close an existing position at market price |
| hyperliquid-funding | Get funding rates for Hyperliquid perp assets, sorted by magnitude |
| hyperliquid-leverage | Set leverage for a Hyperliquid perp asset |
| hyperliquid-limit-order | Place a limit order on Hyperliquid |
| hyperliquid-market-order | Place a market order on Hyperliquid |
| hyperliquid-modify-order | Atomically modify an existing order on Hyperliquid (change price and/or size) |
| hyperliquid-orders | Get open orders for a Hyperliquid account |
| hyperliquid-positions | Get open perp positions for a Hyperliquid account |
| hyperliquid-price | Get Hyperliquid asset price(s) |
| hyperliquid-tp-sl | Place a take-profit or stop-loss trigger order on Hyperliquid |
| cex-account-get-balance | Get detailed per-currency balance breakdown for the connected CEX account |
| cex-account-get-info | Get CEX account summary: total equity (USD), unrealized PnL, net available balance, frozen… |
| cex-futures-cancel-order | Cancel a futures/perpetual order by order ID |
| cex-futures-close-position | Market-close ALL futures positions for an instrument |
| cex-futures-get-positions | Get open futures/perpetual positions with margin health, liquidation risk flags, and… |
| cex-futures-place-order | Place a futures/perpetual order on CEX (leveraged, with long/short) |
| cex-futures-set-leverage | Set leverage multiplier and margin mode (isolated/cross) for a futures instrument |
| cex-market-get-instruments | Get the full list of available trading instruments (spot pairs and futures contracts) on… |
| cex-market-get-kline | Get OHLCV (open/high/low/close/volume) candlestick data for any instrument at a given… |
| cex-market-get-orderbook | Get the live order book (bids and asks with depth) for an instrument |
| cex-market-get-ticker | Get real-time ticker for an instrument: last price, 24h high/low, 24h volume, best bid/ask |
| cex-setup-check | Check whether CEX API credentials are already configured |
| cex-setup-save | Save CEX API key and secret |
| cex-setup-verify | Verify saved CEX credentials by making a live API call |
| cex-spot-cancel-order | Cancel a spot order by order ID |
| cex-spot-get-orders | Get spot order history: open (pending) and historical (filled / cancelled) |
| cex-spot-place-order | Place a spot buy or sell order on CEX (no leverage) |
| data-macro-all | Full US macro snapshot in one call |
| data-price | Get crypto price quotes |
| data-sentiment | Get crypto market sentiment — the Crypto Fear & Greed Index (0-100; 0=Extreme Fear,… |
| data-technicals | Get price-based technical indicators for an asset (currently BTC): RSI (14), MA200 (+… |
| data-derivatives | Get CEX derivatives market structure for an asset (currently BTC): funding rate, futures… |
| data-flows | Get off-chain / market money flow for an asset (currently BTC): spot ETF net flow, Coinbase… |
| data-onchain-defi | Get on-chain DeFi/DEX market structure in one call: total DeFi TVL (all chains + Ethereum),… |
| data-onchain-flows | Get on-chain flow / supply-side indicators for an asset (currently BTC): exchange reserve… |
| data-onchain-valuation | Get on-chain valuation indicators: whether BTC is over/undervalued based on on-chain data —… |
| data-market-structure | Get crypto market structure / relative-strength indicators: BTC dominance (BTC share of… |
| data-defi-protocol | Look up ONE specific DeFi protocol by name or slug (e.g |
| data-events | Get upcoming and recent on-chain events in one call: scheduled token unlocks and recent… |
| data-event-token-unlock | Get upcoming token unlock and vesting schedule events |
| data-token-info | Query detailed token/project information by name or symbol |
| crypto-kol-signals | Get KOL creators and news discussing one specific token |
| crypto-mention-surge | Detect tokens with sudden social attention shifts |
| crypto-sentiment-score | Get social sentiment for one specific token |
| crypto-social-trending | Get a ranked list of tokens by social activity (AltRank — composite of |
| wallet-guard-address-security | Check if a wallet address is flagged malicious across 12+ categories: hacker, scammer,… |
| wallet-guard-approval-security | Scan a wallet for dangerous token/NFT approvals: unlimited ERC20 allowances, suspicious… |
| wallet-guard-nft-security | Detect NFT collection contract risks: transfer locks, trading pause, blacklist controls,… |
| wallet-guard-phishing-site | Check if a URL is a phishing or impersonation website |
| wallet-guard-token-deep-scan | Comprehensive token security analysis with 0–100 risk score and scenario classification… |
| wallet-balance-query | Query native token balance for a wallet address across all supported blockchains |
| airdrop-check-project | Deep-dive analysis of ONE specific named airdrop project |
| airdrop-daily-report | Get today's pre-curated airdrop digest: top S/A-grade picks, zero-cost options, upcoming… |
| airdrop-scam-check | Check whether a specific URL is a phishing site or fake airdrop claim page |
| airdrop-scan | Sweep the market for ALL currently active airdrop projects |
| airdrop-zero-cost | Find airdrops that require zero capital: gas-free testnets and free mainnet tasks |
| easy-mining-create-task-batch | Create a batch task across multiple miners: reboot, power mode change, firmware upgrade,… |
| easy-mining-get-task-batch | Get status and per-miner results for a specific task batch |
| easy-mining-get-workspace | Verify API connectivity and get workspace metadata (name, ID) |
| easy-mining-list-agents | List Nonce automation agents: IDs, names, status |
| easy-mining-list-farms | List all mining farms and their IDs |
| easy-mining-list-history | Historical performance for ONE specific miner: hashrate curve, power, temperature, uptime |
| easy-mining-list-metrics-history | Daily historical metrics for an entire FARM: aggregate hashrate, online count, BTC earnings… |
| easy-mining-list-miner-tasks | Task execution history for ONE specific miner: reboots, firmware upgrades, pool changes and… |
| easy-mining-list-miners | Real-time status of ALL miners in a farm: hashrate, power, temperature, model |
| easy-mining-list-pool-diffs | Pool configuration change records for a farm: when and what pool settings changed |
| easy-mining-list-task-batches | List all task batches for a farm (paginated) |
| meme-analyze | Analyze a meme token's 'wealth gene' — 4-dimensional assessment (narrative strength,… |
| investor_analyze | Deep analysis of a specific DeFi earn product — historical APY/TVL, LLM risk insights,… |
| investor_compare | Side-by-side comparison of 2–5 DeFi opportunities: APY, TVL, risk score, chain, protocol… |
| investor_discover | Search DeFi yield opportunities by natural language or filters (chain, protocol type, min… |
| transfer-cancel | Cancel a pending transfer session before the user signs |
| transfer-request | Prepare and confirm a Web3 on-chain transfer — sending tokens FROM user's address TO… |
| transfer-status | Track a transfer session by session_id: phase (prepare/signing/broadcasting/confirmed),… |
| settlement-gas | Gas/fee outlook for a chain |
| settlement-pending-pool | Analyze a specific DEX liquidity pool for sandwich attack (MEV) risk and return a safe… |
| settlement-track-tx | Track a transaction by hash — auto-detects EVM vs Bitcoin from the hash format |
| settlement-verify-contract | Check if an EVM smart contract's source code is verified on Etherscan and flag security… |
| event-feed-detail | Fetch the complete card for ONE event using a known eventId |
| event-feed-list | Browse the curated Antalpha Event Feed: top-N heat-score-ranked prediction events across… |
| event-feed-prompts | Return 2–3 AI-generated follow-up question strings for a known eventId |
| get_trade_quotes | Aggregate A-class (in-app: 0x swap-full, 1inch smart-swap-create, HL… |
| execute_trade | Execute a selected route after get_trade_quotes |
| web-search-extract | Extract the main readable content from a specific URL via Exa |
| web-search-query | Real-time web search via Tavily/Exa |
| test-ping | Connectivity test — confirms MCP server is reachable |

## Troubleshooting
- If tools aren't appearing in your client, verify the MCP server URL is correctly entered
- For authentication issues, confirm your agent is properly registered with Antalpha
- For rate limiting errors, check with the Antalpha team about adjusting your limits
- If specific tools return errors, check that you're providing all required parameters
- For wallet-related tools, ensure you're using valid wallet addresses
- If experiencing connectivity issues, verify your network connection and firewall settings allow outbound connections to the Antalpha server