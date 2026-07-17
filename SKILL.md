---
name: antalpha-ai-setup
description: Install and configure the Antalpha Skills MCP server. Provides 120+ Web3 tools for DEX swaps, smart money tracking, Polymarket prediction markets, Hyperliquid perpetuals, CEX trading, Bitcoin mining, and DeFi analytics.
version: 2.1.0
author: Antalpha Labs
homepage: https://mcp-skills.ai.antalpha.com
---

# Antalpha Skills MCP Server Setup

## Overview
The Antalpha Skills MCP server provides 120+ Web3 tools for AI agents, including DEX swaps, smart money tracking, Polymarket prediction markets, Hyperliquid perpetuals, CEX trading, Bitcoin mining, and DeFi analytics. This server enables AI agents to interact with various Web3 protocols through a unified Model Context Protocol (MCP) interface.

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
The server currently exposes **129 tools** (120+). This list is generated from the live MCP `tools/list` endpoint — run `npx mcporter list https://mcp-skills.ai.antalpha.com/mcp` for the always-current set.
### Session
| Tool | Description |
|------|-------------|
| antalpha-register | Register this agent with Antalpha platform. Returns agent_id required by Polymarket tools |
| test-ping | Connectivity test — confirms MCP server is reachable. Returns server time (UTC+8) |

### DEX Swaps
| Tool | Description |
|------|-------------|
| swap-quote | Get a DEX swap quote: expected output amount, minimum receive after slippage, gas estimate,… |
| swap-full | Execute a DEX token swap end-to-end: gets firm quote + generates signing page + hosts it. Re… |
| swap-create-page | Generate a DEX swap signing page from an existing quote. Returns preview_url. Rare — only us… |
| swap-tokens | List all supported DEX tokens: symbol, name, contract address, decimals. Reference lookup on… |
| swap-gas | Get a quick gas estimate (Gwei + units) scoped specifically to the current swap. Single-valu… |
| smart-swap-create | Create a 1inch Fusion (Dutch auction) MEV-protected swap order. Returns signing URL. Auction… |
| smart-swap-list | List all smart swap orders for a wallet: active (in auction), filled, cancelled |
| smart-swap-status | Check current execution status of a smart swap order: auction progress, fill percentage, exe… |
| smart-swap-cancel | Check the cancellation or expiry status of a 1inch Fusion smart swap order. Fusion orders au… |
| jupiter-swap-quote | Get a Solana (Jupiter) swap quote: expected output, price impact and route |
| jupiter-swap-tokens | List supported Solana tokens for Jupiter swaps: symbol, mint address, decimals |
| jupiter-trigger-list | List Jupiter trigger (limit) orders for a Solana wallet |
| xstock-pool-snapshot | Snapshot of an xStock tokenized-equity liquidity pool on Solana |
| get_trade_quotes | Fetch and compare executable trade-route quotes for a single spot/futures trade intent acros… |
| execute_trade | Execute a previously quoted on-chain trade route by producing a non-custodial browser signin… |

### CEX Trading (OKX/Binance)
| Tool | Description |
|------|-------------|
| cex-market-quote | Public market data for OKX / Binance — `view` selects the feed. view=ticker (default): real-… |
| cex-market-get-instruments | Get the full list of available trading instruments (spot pairs and futures contracts) on the… |
| cex-account | Read a CEX account (OKX or Binance) — `view` selects granularity. view=balance (default): PE… |
| cex-setup-check | Check whether CEX API credentials are already configured. Returns ready / not-ready status |
| cex-spot-place-order | Place a spot buy or sell order on CEX (no leverage) |
| cex-spot-cancel-order | Cancel a spot order by order ID |
| cex-spot-get-orders | Get spot order history: open (pending) and historical (filled / cancelled) |
| cex-futures-place-order | Place a futures/perpetual order on CEX (leveraged, with long/short). Supports semantic input… |
| cex-futures-cancel-order | Cancel a futures/perpetual order by order ID |
| cex-futures-get-positions | Get open futures/perpetual positions with margin health, liquidation risk flags, and unreali… |
| cex-futures-set-leverage | Set leverage multiplier and margin mode (isolated/cross) for a futures instrument. Affects a… |
| cex-futures-close-position | Market-close ALL futures positions for an instrument. Full exit |

### Hyperliquid Perps
| Tool | Description |
|------|-------------|
| hyperliquid-market | Hyperliquid perp market data — `view` selects the feed. view=price (default): mark price for… |
| hyperliquid-account | Get Hyperliquid account summary: balances, positions, open orders |
| hyperliquid-orders | Get open orders for a Hyperliquid account |
| hyperliquid-positions | Get open perp positions for a Hyperliquid account |
| hyperliquid-balance-check | Pre-check if account has sufficient balance for a trade. order_type=""spot"" checks Spot USD… |
| hyperliquid-limit-order | Place a limit order on Hyperliquid. Requires agent_key and owner address |
| hyperliquid-market-order | Place a market order on Hyperliquid. Requires agent_key and owner address |
| hyperliquid-close | Close an existing position at market price. Requires agent_key and owner |
| hyperliquid-cancel | Cancel an open order on Hyperliquid |
| hyperliquid-leverage | Set leverage for a Hyperliquid perp asset |
| hyperliquid-tp-sl | Place a take-profit or stop-loss trigger order on Hyperliquid |
| hyperliquid-modify-order | Atomically modify an existing order on Hyperliquid (change price and/or size) |

### Polymarket
| Tool | Description |
|------|-------------|
| poly-markets | Polymarket market discovery & lookup — one tool, four views via `view`. view=trending (defau… |
| poly-portfolio | Read a Polymarket wallet's portfolio — `view` selects the slice. view=positions (default): c… |
| poly-buy | Buy outcome tokens on Polymarket. Returns signing URL. Zero custody — private keys never lea… |
| poly-sell | Sell outcome tokens on Polymarket. Returns signing URL. Zero custody |
| poly-order-status | Check PolyMaster / Polymarket orders. Give order_id to fetch ONE order's signing status (pen… |
| poly-strategy | PolyMaster logical-implication hedge strategy — `action` selects the operation. action=scan… |
| poly-master-traders | Polymarket trader intelligence (Arkham-backed cache) — `view` selects the lens. view=rank (d… |
| poly-master-follow | Follow or unfollow a Polymarket trader. Set copy ratio (e.g. 0.5 = copy at 50% size) |
| poly-master-status | Single-call copy-trading dashboard: followed traders, recent orders, current risk config |
| poly-master-risk | View or update copy-trading risk limits: max position size, daily loss limit, copy ratio caps |
| poly-master-pnl | PnL report for copy-trading: breakdown by daily/weekly/total and by followed trader |

### Smart Money
| Tool | Description |
|------|-------------|
| smart-money-signal | Get aggregated trading signals from ALL monitored wallets. HIGH = buy >$50K or first positio… |
| smart-money-watch | View a single wallet's recent on-chain activity. Works for ANY address: a wallet on your wat… |
| smart-money-list | View / list the wallets currently being monitored — the pre-loaded public smart-money wallet… |
| smart-money-custom | Manage your smart-money watchlist & settings — add or remove a private wallet (max 5), get/u… |
| smart-money-pool | View LP (liquidity provider) activity for smart money addresses: pool add/remove events, tok… |
| smart-money-token-scan | Token-centric whale scan: given a TOKEN (contract 0x… or symbol), return its top holders wit… |

### Wallet Security
| Tool | Description |
|------|-------------|
| wallet-guard-address-security | Check if a wallet address is flagged malicious across 12+ categories: hacker, scammer, sanct… |
| wallet-guard-approval-security | Scan a wallet for dangerous token/NFT approvals: unlimited ERC20 allowances, suspicious spen… |
| wallet-guard-nft-security | Detect NFT collection contract risks: transfer locks, trading pause, blacklist controls, fak… |
| wallet-guard-phishing-site | Check if a URL is a phishing or impersonation website. Output: safe/warning/critical verdict |
| wallet-guard-token-deep-scan | Comprehensive token security analysis with 0–100 risk score and scenario classification (Sta… |
| wallet-revoke-page | Generate a browser-openable page to REVOKE risky ERC-20 approvals by sending approve(spender… |

### Wallet Analytics
| Tool | Description |
|------|-------------|
| wallet-balance-query | Query native token balance for a wallet address across all supported blockchains. Auto-detec… |
| wallet-activity-query | Fetch EVM wallet transaction history (sends, receives, trades, approvals) across all support… |
| wallet-tx-history | Transaction profile for a wallet from on-chain history: type distribution, distinct counterp… |
| wallet-pnl | Realized PnL / ROI / win rate / traded counts + top tokens for a wallet over a date window (… |
| wallet-counterparties | Labeled top counterparties for a wallet over a date window (Nansen): entity / smart-money la… |

### DeFi Yield
| Tool | Description |
|------|-------------|
| investor_discover | Discover yield opportunities across DeFi, RWA, CeFi and commodity products. When asset_class… |
| investor_analyze | Deep analysis of a specific DeFi earn product — historical APY/TVL, LLM risk insights, confi… |
| investor_compare | Compare two to five yield products by APY, risk, TVL, eligibility, deposit assets, redemptio… |
| investor_position_checkup | Evaluate existing yield positions against the curated catalog and suggest safer or higher-yi… |

### Market Data & Macro
| Tool | Description |
|------|-------------|
| data-price | Get crypto price quotes. asset='btc' → BTC price + valuation/level anchors (MA200, RSI, AHR9… |
| data-sentiment | Get crypto market sentiment — the Crypto Fear & Greed Index (0-100; 0=Extreme Fear, 100=Extr… |
| data-macro-all | Full US macro snapshot in one call. Returns LATEST values for 12 core indicators: cpi, nfp,… |
| data-derivatives | Get CEX derivatives market structure for an asset: funding rate, futures premium (annualized… |
| data-technicals | Get price-based technical indicators for an asset (currently BTC): RSI (14), MA200 (+ deviat… |
| data-funding-scan | Scan the WHOLE crypto market for cross-exchange perpetual funding-rate dislocations — the da… |
| data-flows | Get off-chain / market money flow for BTC: spot ETF net flow, Coinbase premium (US instituti… |
| data-onchain-flows | Get on-chain flow / supply-side indicators for an asset (currently BTC): exchange reserve (t… |
| data-onchain-defi | Get on-chain DeFi/DEX market structure in one call: total DeFi TVL (all chains + Ethereum),… |
| data-onchain-valuation | Get on-chain valuation indicators: whether BTC is over/undervalued based on on-chain data —… |
| data-market-structure | Get crypto market structure / relative-strength indicators: BTC dominance (BTC share of tota… |
| data-defi-protocol | Look up ONE specific DeFi protocol by name or slug (e.g. morpho, aave, aave-v3). Returns a p… |
| data-token-info | Look up any crypto token or project by symbol or name (e.g. HYPE, PEPE, Hyperliquid). Return… |
| data-events | Get upcoming and recent on-chain events in one call: scheduled token unlocks and recent secu… |
| data-event-token-unlock | Get upcoming token unlock events in the next 30 days, ranked by USD value, sourced from Defi… |

### Tokenized US Stocks
| Tool | Description |
|------|-------------|
| us-stock-bundle | One-shot single-stock bundle — the primary path for analyzing one tokenized US stock. Return… |
| us-stock-financials | Financials of a tokenized US stock: earnings calendar (next_report_date, days_to_earnings) +… |
| us-stock-technicals | Price performance & technicals of a tokenized US stock, from EOD adjusted prices (NOT real-t… |
| us-stock-onchain | On-chain premium/discount of a tokenized US stock vs its underlying, per platform, with wher… |
| us-stock-sector | US sector overview: whole-market GICS sector P/E & recent performance (FMP aggregate, NOT po… |
| us-stock-dcf | DCF intrinsic value of a tokenized US stock: base-case intrinsic value & upside-vs-price, ke… |

### Social Intel
| Tool | Description |
|------|-------------|
| crypto-social-trending | Ranked list of crypto tokens by social activity (AltRank — composite of social volume × mark… |
| crypto-sentiment-score | Social sentiment for ONE crypto token/coin (e.g. BTC, ETH, SOL), from LunarCrush social data… |
| crypto-kol-signals | Who is discussing ONE crypto token and what they're saying, from LunarCrush. Crypto tokens O… |
| crypto-mention-surge | Detect crypto tokens with sudden social attention shifts (AltRank jumps), from LunarCrush. C… |

### Airdrops
| Tool | Description |
|------|-------------|
| airdrop-scan | Sweep the market for ALL currently active airdrop projects. Returns a filterable ranked list… |
| airdrop-daily-report | Get today's pre-curated airdrop digest: top S/A-grade picks, zero-cost options, upcoming dea… |
| airdrop-check-project | Deep-dive analysis of ONE specific named airdrop project. Grades it S/A/B/C on VC quality, f… |
| airdrop-zero-cost | Find airdrops that require zero capital: gas-free testnets and free mainnet tasks. Returns t… |
| airdrop-scam-check | Check whether a specific URL is a phishing site or fake airdrop claim page. Returns SAFE / W… |

### Bitcoin Mining
| Tool | Description |
|------|-------------|
| easy-mining-get-workspace | Verify API connectivity and get workspace metadata (name, ID) |
| easy-mining-list-farms | List all mining farms and their IDs. farm_id is required by most other easy-mining tools |
| easy-mining-list-agents | List Nonce automation agents: IDs, names, status |
| easy-mining-list-miners | Real-time status of ALL miners in a farm: hashrate, power, temperature, model. Primary healt… |
| easy-mining-list-metrics-history | Daily historical metrics for an entire FARM: aggregate hashrate, online count, BTC earnings… |
| easy-mining-list-pool-diffs | Pool configuration change records for a farm: when and what pool settings changed |
| easy-mining-list-history | Historical performance for ONE specific miner: hashrate curve, power, temperature, uptime. F… |
| easy-mining-list-miner-tasks | Task execution history for ONE specific miner: reboots, firmware upgrades, pool changes and… |
| easy-mining-list-task-batches | List all task batches for a farm (paginated). Use to find task_batch_id for status checks |
| easy-mining-create-task-batch | Create a batch task across multiple miners: reboot, power mode change, firmware upgrade, poo… |
| easy-mining-get-task-batch | Get status and per-miner results for a specific task batch |

### Transfer & Settlement
| Tool | Description |
|------|-------------|
| transfer-request | Prepare and confirm a Web3 on-chain transfer — sending tokens FROM user's address TO another… |
| transfer-status | Track a transfer session by session_id: phase (prepare/signing/broadcasting/confirmed), tx_h… |
| transfer-cancel | Cancel a pending transfer session before the user signs. Input: session_id from transfer-req… |
| settlement-gas | Gas/fee outlook for a chain. EVM (ethereum/arbitrum/optimism/base/polygon): current gas tier… |
| settlement-pending-pool | Analyze a specific DEX liquidity pool for sandwich attack (MEV) risk and return a safe slipp… |
| settlement-track-tx | Track a transaction by hash — auto-detects EVM vs Bitcoin from the hash format. EVM (0x + 64… |
| settlement-verify-contract | Check if an EVM smart contract's source code is verified on Etherscan and flag security risk… |

### Events & Predictions
| Tool | Description |
|------|-------------|
| event-feed-list | Browse the curated Antalpha Event Feed: top-N heat-score-ranked prediction events across POL… |
| event-feed-detail | Fetch the complete card for ONE event using a known eventId. Returns: heatScore, |
| event-feed-prompts | Return 2–3 AI-generated follow-up question strings for a known eventId. For UI chip renderin… |
| oracle-match-search | Find a specific 2026 FIFA World Cup match (single fixture, e.g. 'Portugal vs Croatia') by te… |
| oracle-event-detail | Get full detail for one 2026 FIFA World Cup prediction event |

### Meme & Web Search
| Tool | Description |
|------|-------------|
| meme-analyze | Analyze a meme token's 'wealth gene' — 4-dimensional assessment (narrative strength, communi… |
| web-search-query | Real-time web search via Tavily/Exa. Use when the user asks a general-knowledge question req… |
| web-search-extract | Extract the main readable content from a specific URL via Exa. Use when the user provides a… |

## Troubleshooting
- If tools aren't appearing in your client, verify the MCP server URL is correctly entered
- For authentication issues, confirm your agent is properly registered with Antalpha
- For rate limiting errors, check with the Antalpha team about adjusting your limits
- If specific tools return errors, check that you're providing all required parameters
- For wallet-related tools, ensure you're using valid wallet addresses
- If experiencing connectivity issues, verify your network connection and firewall settings allow outbound connections to the Antalpha server