[🇺🇸 English](#english) · [🇨🇳 中文](#chinese)

---

<a name="english"></a>

# Antalpha AI Setup

Setup guide for the Antalpha Skills MCP Server — 120+ Web3 tools across DEX & CEX trading, Hyperliquid perpetuals, smart money tracking, Polymarket prediction markets, wallet security, tokenized US stocks, DeFi analytics, and real-time market data.

## What is this?

An [OpenClaw](https://github.com/openclaw/openclaw) skill that connects your AI agent to the Antalpha Skills MCP server with 120+ tools.

## Quick Install

### Option 1: mcporter (Recommended)

```bash
npx mcporter list https://mcp-skills.ai.antalpha.com/mcp --name antalpha
```

Output:

```
✓ MCP server "antalpha" connected

→ Registering agent...
 ✓ agent_id: "a3f1c8e7-4d2b-4a9f-b6e5-7c8d9e0f1a2b"
 ✓ api_key: "sk_4f7a2e...b2c3d4e5f6a7b8c9d"

 129 tools ready.
```

> Then add the returned `agent_id` and `api_key` to your MCP client config.

### Option 2: OpenClaw Skill Install

```bash
openclaw skill install https://github.com/AntalphaAI/antalpha-ai-setup
```

## MCP Server URL

```
https://mcp-skills.ai.antalpha.com/mcp
```

## Supported Clients

- Claude.ai (web)
- Claude Code (terminal)
- Codex (terminal)
- Claude Desktop / Cursor / Windsurf
- Gemini CLI
- OpenCode
- OpenClaw

## What You Get

120+ tools across these categories:

- **DEX & Solana Swaps** — swap-quote, swap-full, smart-swap-*, jupiter-swap-quote — *"Get a quote for 1 ETH to USDC"*
- **CEX Trading (OKX / Binance)** — cex-market-quote, cex-spot-place-order, cex-futures-place-order — *"Buy 0.1 BTC spot on OKX"*
- **Hyperliquid Perps** — hyperliquid-positions, hyperliquid-limit-order, hyperliquid-market-order — *"Show my perp positions"*
- **Polymarket** — poly-markets, poly-buy, poly-master-* — *"What's trending on Polymarket?"*
- **Smart Money** — smart-money-signal, smart-money-watch, smart-money-token-scan — *"Show whale trading signals"*
- **Wallet Security & Analytics** — wallet-guard-*, wallet-pnl, wallet-revoke-page — *"Scan my wallet for risky approvals"*
- **DeFi Yield** — investor_discover, investor_analyze, investor_compare — *"Find stablecoin yields above 5%"*
- **Market Data & Macro** — data-price, data-derivatives, data-funding-scan, data-macro-all — *"BTC funding rates across exchanges"*
- **Tokenized US Stocks** — us-stock-bundle, us-stock-financials, us-stock-dcf — *"Analyze tokenized AAPL"*
- **Airdrops & Social Intel** — airdrop-scan, crypto-social-trending, crypto-kol-signals — *"Any active airdrops today?"*
- **Bitcoin Mining** — easy-mining-list-miners, easy-mining-create-task-batch — *"Show my mining farm status"*
- **Settlement, Transfer & Events** — settlement-gas, transfer-request, event-feed-list — *"What's the gas on Arbitrum?"*

See [SKILL.md](./SKILL.md) for the full tool reference.

## Related

- [Antalpha MCP Documentation](https://www.antalpha.com/documentation)
- [Antalpha Website](https://www.antalpha.com/)

## License

MIT

---

<a name="chinese"></a>

# Antalpha AI Setup（中文）

Antalpha Skills MCP 服务器安装指南 —— 120+ Web3 工具，覆盖 DEX & CEX 交易、Hyperliquid 永续合约、聪明钱追踪、Polymarket 预测市场、钱包安全、代币化美股、DeFi 分析和实时市场数据。

## 这是什么？

一个 [OpenClaw](https://github.com/openclaw/openclaw) Skill，帮助你的 AI Agent 接入 Antalpha Skills MCP 服务器，解锁 120+ 个 Web3 工具。

## 快速安装

### 方式一：mcporter（推荐）

```bash
npx mcporter list https://mcp-skills.ai.antalpha.com/mcp --name antalpha
```

输出示例：

```
✓ MCP server "antalpha" connected

→ Registering agent...
 ✓ agent_id: "a3f1c8e7-4d2b-4a9f-b6e5-7c8d9e0f1a2b"
 ✓ api_key: "sk_4f7a2e...b2c3d4e5f6a7b8c9d"

 129 tools ready.
```

> 将返回的 `agent_id` 和 `api_key` 配置到你的 MCP 客户端即可。

### 方式二：OpenClaw Skill 安装

```bash
openclaw skill install https://github.com/AntalphaAI/antalpha-ai-setup
```

## MCP 服务器地址

```
https://mcp-skills.ai.antalpha.com/mcp
```

## 支持的客户端

- Claude.ai（网页版）
- Claude Code（终端）
- Codex（终端）
- Claude Desktop / Cursor / Windsurf
- Gemini CLI
- OpenCode
- OpenClaw

## 工具分类（120+）

- **DEX & Solana 兑换** — swap-quote、swap-full、smart-swap-*、jupiter-swap-quote — *"查询 1 ETH 兑换 USDC 的报价"*
- **CEX 交易（OKX / Binance）** — cex-market-quote、cex-spot-place-order、cex-futures-place-order — *"在 OKX 现货买入 0.1 BTC"*
- **Hyperliquid 永续合约** — hyperliquid-positions、hyperliquid-limit-order、hyperliquid-market-order — *"查看我的永续仓位"*
- **Polymarket 预测市场** — poly-markets、poly-buy、poly-master-* — *"当前 Polymarket 热门市场有哪些？"*
- **聪明钱追踪** — smart-money-signal、smart-money-watch、smart-money-token-scan — *"查看鲸鱼交易信号"*
- **钱包安全 & 分析** — wallet-guard-*、wallet-pnl、wallet-revoke-page — *"扫描我的钱包高风险授权"*
- **DeFi 投资** — investor_discover、investor_analyze、investor_compare — *"发现年化 5% 以上的稳定币机会"*
- **市场数据 & 宏观** — data-price、data-derivatives、data-funding-scan、data-macro-all — *"各交易所 BTC 资金费率"*
- **代币化美股** — us-stock-bundle、us-stock-financials、us-stock-dcf — *"分析代币化 AAPL"*
- **空投 & 社交情报** — airdrop-scan、crypto-social-trending、crypto-kol-signals — *"今天有活跃空投吗？"*
- **比特币挖矿** — easy-mining-list-miners、easy-mining-create-task-batch — *"查看我的矿场状态"*
- **结算、转账 & 事件** — settlement-gas、transfer-request、event-feed-list — *"查询 Arbitrum 当前 gas 费"*

完整工具清单见 [SKILL.md](./SKILL.md)。

## 相关链接

- [Antalpha MCP 文档](https://www.antalpha.com/documentation)
- [Antalpha 官网](https://www.antalpha.com/)

## 许可证

MIT
