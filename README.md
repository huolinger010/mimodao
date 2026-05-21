<div align="center">

# 🏛️ MiMoDAO

### Real-Time DAO Governance Intelligence — Powered by Xiaomi MiMo V2.5

Score live Snapshot proposals across 7 risk dimensions, forecast vote outcomes with confidence rings, surface trending proposals from 20 top DAOs by participation velocity, and draft governance documents in seconds. All in a single zero-dependency HTML file.

[![Live Demo](https://img.shields.io/badge/▶_Live_Demo-22c55e?style=for-the-badge&logo=githubpages&logoColor=white)](https://huolinger010.github.io/mimodao/)
[![MiMo V2.5](https://img.shields.io/badge/Powered_by-Xiaomi_MiMo_V2.5-ff6b00?style=for-the-badge)](https://platform.xiaomimimo.com)
[![Snapshot](https://img.shields.io/badge/Live_Data-Snapshot_GraphQL-5563f5?style=for-the-badge)](https://snapshot.org)
[![License](https://img.shields.io/badge/License-MIT-3b82f6?style=for-the-badge)](LICENSE)

[![Stars](https://img.shields.io/github/stars/huolinger010/mimodao?style=flat-square&color=fbbf24)](https://github.com/huolinger010/mimodao/stargazers)
[![Issues](https://img.shields.io/github/issues/huolinger010/mimodao?style=flat-square&color=a78bfa)](https://github.com/huolinger010/mimodao/issues)
[![Last Commit](https://img.shields.io/github/last-commit/huolinger010/mimodao?style=flat-square&color=34d399)](https://github.com/huolinger010/mimodao/commits)
[![Single HTML](https://img.shields.io/badge/Single_File-No_Dependencies-c084fc?style=flat-square)](#-architecture)

</div>

---

## 📖 Overview

DAO governance is broken at the read-layer. Proposals stretch thousands of words, treasury impacts hide in spec footnotes, and most token holders skip the read entirely — leading to low-context votes and rubber-stamp outcomes. Multi-billion-dollar protocols like Uniswap, Aave, and Arbitrum suffer single-digit voter turnout, and quality decisions hinge on a handful of delegates with the time to actually digest the document.

**MiMoDAO closes that gap.** It runs a five-agent pipeline directly on Snapshot's live GraphQL feed, scoring proposals across seven analytical dimensions, predicting vote outcomes with confidence intervals, surfacing the hottest active proposals across the entire DAO ecosystem, and drafting structured governance documents from a one-line idea — all powered by Xiaomi MiMo V2.5 and rendered in a single, dependency-free HTML file.

No backend. No build step. No registration. No vendor lock-in. Open the page and start governing better.

## ✨ Core Features

### 🔍 Proposal Analyzer
Multi-dimensional risk scoring on every active or closed proposal across 20 top DAOs — pull the proposal, parse the body, run seven scoring rubrics, and produce a vote recommendation with risk verdict.

- **Seven scoring axes** — Complexity, Financial Impact, Security, Governance, Technical, Urgency, Sentiment
- **Risk verdict** — Low / Medium / High with color-coded confidence
- **Vote recommendation** — FOR / AGAINST / ABSTAIN with rationale and key metrics
- **Live vote bars** — current distribution + total participation
- **Tag classification** — Treasury Impact, Security, Governance, Technical, Urgency, Active Voting, High Participation
- **Share card** — generate a screenshot-ready summary card for Twitter/Lens

### 🔮 Vote Predictor
Real-time outcome forecasting based on live vote distribution, lead margin, and time-to-close.

- **Confidence ring** — animated SVG indicator (0-100%) calibrated by margin and total participation
- **Winner forecast** — predicted winning option with vote percentage and lead margin
- **Momentum tag** — Strong Lead / Leading / Steady / Tight Race based on margin × time remaining
- **Per-choice breakdown** — animated bars showing vote distribution across all options

### 🔥 Trending Feed
Cross-DAO ranking of the hottest active proposals — sorted by participation momentum, not raw vote count.

- **Heat scoring** — velocity (votes per hour) × urgency (time-to-close)
- **Log-scaled visualization** — meaningful heat values across all 20 ranks
- **Live stats** — total active proposals, active DAOs, aggregate vote count
- **Top-3 highlight** — gradient rank badges for the most active proposals
- **One-click jump** — tap any trending card to load the analyzer view

### ✍️ Governance Writer
Plain-language idea in, forum-ready proposal out.

- **Structured output** — Summary, Motivation, Specification, Budget, Timeline, Success Metrics, Risk Mitigations
- **Five proposal types** — General Governance, Treasury / Funding, Technical Upgrade, Partnership, Parameter Change
- **Type-aware templates** — budget tables for treasury, audit cycles for technical, due diligence for partnerships
- **Copy-paste ready** — markdown output formatted for Snapshot, Discourse, Commonwealth, or any DAO forum

### 🌍 Global Search (⌘K)
Instant fuzzy search across 200 latest proposals from every indexed DAO.

- **Cmd+K / Ctrl+K** — keyboard-native command palette
- **60-second cache** — sub-second results after first query
- **Fuzzy match** — title and DAO name across active, pending, and closed proposals
- **Live state indicators** — color-coded active / pending / closed badges
- **Click-through** — open any result directly in the analyzer

### 📊 Voting Power Checker
Drop in any Ethereum address or ENS name and see voting power across every supported DAO.

- **Multi-DAO query** — single API call returns voting power for all spaces in parallel
- **ENS resolution** — paste `vitalik.eth` instead of hex addresses
- **Per-DAO cards** — token balance, voting power, delegation status

### 📋 Personal Dashboard
Active proposals from your favorite DAOs, all in one feed.

- **Favorites system** — star DAOs and individual proposals (LocalStorage-backed)
- **Smart filters** — All / Active / Ending Soon / High Participation
- **At-a-glance stats** — total favs, active count, ending in 24h

## 🛠️ Tech Stack

| Layer | Technology | Notes |
|-------|-----------|-------|
| Frontend | Vanilla HTML + CSS + JS | Zero dependencies, single file, ~110 KB |
| AI Engine | [Xiaomi MiMo V2.5](https://platform.xiaomimimo.com) | `mimo-v2.5-pro` for analysis and writing |
| Data Source | [Snapshot.org GraphQL](https://hub.snapshot.org/graphql) | Free, no API key required |
| Hosting | GitHub Pages | Static, instant CDN |
| Theming | CSS variables + `prefers-color-scheme` | Dark / light auto-toggle, glassmorphism |
| State | LocalStorage | Favorites, theme preference |
| Identity | ENS resolution via [stamp.fyi](https://stamp.fyi) | DAO avatars, no central API |

## 🏗️ Architecture

```
┌────────────────────────────────────────────────────────────────┐
│                  MiMoDAO (single index.html)                   │
├────────────────────────────────────────────────────────────────┤
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────────┐    │
│  │ Analyzer │  │ Predictor│  │ Trending │  │   Writer     │    │
│  │ 7-axis   │  │ Confidence│ │ Heat-rank│  │ 5 templates  │    │
│  │ scoring  │  │  + Momentum│ │ + Velocity│ │  Markdown    │    │
│  └────┬─────┘  └─────┬────┘  └─────┬────┘  └──────┬───────┘    │
│       │              │             │              │            │
│       ▼              ▼             ▼              ▼            │
│  ┌──────────────────────────────────────────────────────┐      │
│  │     Snapshot GraphQL (free)  +  MiMo V2.5 API        │      │
│  └──────────────────────────────────────────────────────┘      │
│                                                                │
│  ┌─────────────┐    ┌─────────────────┐   ┌──────────────┐     │
│  │ Global Search│    │ Voting Power    │  │  Dashboard   │     │
│  │   ⌘K modal   │    │ ENS multi-DAO   │  │  Favs + Filter│    │
│  └─────────────┘    └─────────────────┘   └──────────────┘     │
└────────────────────────────────────────────────────────────────┘
```

Everything is client-side. No server, no database, no telemetry. The browser is the entire stack.

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/huolinger010/mimodao.git
cd mimodao

# Option 1: Open directly in your browser
open index.html

# Option 2: Serve locally with any static server
python3 -m http.server 8000
# → http://localhost:8000

# Option 3: Use the live demo
# → https://huolinger010.github.io/mimodao/
```

No `npm install`. No build step. No environment variables for browsing. Bring your own MiMo V2.5 API key only if you want to enable AI-powered drafting and Q&A.

## 📋 Supported DAOs

ENS · Uniswap · Aave DAO · Lido · Arbitrum DAO · Optimism Collective · Gitcoin · SafeDAO · Curve Finance · Balancer · dYdX · Sushi · Nouns · Morpho · ApeCoin DAO · GnosisDAO · Starknet · Radiant Capital · CoW DAO · 1inch Network — and any custom Snapshot space ID via Trending or Global Search.

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `⌘K` / `Ctrl+K` | Open global proposal search |
| `Esc` | Close search modal / close analysis |
| `Tab` | Navigate between tabs |

## 🎯 Roadmap

- [ ] Voting power simulator with delegate-aware projection
- [ ] Multi-DAO portfolio dashboard with treasury health metrics
- [ ] On-chain treasury tracking via Etherscan / Blockscout
- [ ] Proposal alert bot for Telegram / Discord
- [ ] Snapshot proposal subscription via WebSocket
- [ ] CSV export of analysis results
- [ ] PDF report generation for governance reviews

## 🤝 Contributing

PRs and issues welcome. When contributing, keep changes scoped to the agent boundary you're working in (Analyzer, Predictor, Trending, Writer, Search, Wallet, or Dashboard), document new scoring rules with the same paragraph style as existing analysis, and verify your changes against at least three different DAOs before submitting.

```bash
# Verify Snapshot GraphQL still resolves the spaces you're using
curl -s -X POST https://hub.snapshot.org/graphql \
  -H "Content-Type: application/json" \
  -d '{"query":"query{spaces(where:{id_in:[\"ens.eth\"]}){id name proposalsCount}}"}'
```

## 📄 License

[MIT](LICENSE) © 2026 [@huolinger010](https://github.com/huolinger010)

## 🙏 Acknowledgements

- [**Xiaomi MiMo Team**](https://platform.xiaomimimo.com) — for shipping a V2.5 model that runs governance reasoning at zero cost to end users
- [**Snapshot Labs**](https://snapshot.org) — for keeping DAO data open and queryable without API keys
- [**stamp.fyi**](https://stamp.fyi) — for free ENS / DAO avatar resolution
- The 20+ DAOs whose live proposals make MiMoDAO actually useful

---

<div align="center">

**Built for the [Xiaomi MiMo Orbit 100T Token Creator Program](https://100t.xiaomimimo.com/)** 🚀

*Better governance starts with better reads.*

</div>
