<div align="center">

# 🏛️ MiMoDAO

**DAO Governance Intelligence — Powered by Xiaomi MiMo V2.5**

Score live Snapshot proposals across 7 risk dimensions, draft professional governance docs, and explore 30+ top DAOs — all in a single HTML file. Zero backend, no API key.

[![Live Demo](https://img.shields.io/badge/Live-Demo-22c55e?style=for-the-badge&logo=githubpages&logoColor=white)](https://huolinger010.github.io/mimodao/)
[![MiMo V2.5](https://img.shields.io/badge/MiMo-V2.5-ff6b00?style=for-the-badge)](https://platform.xiaomimimo.com)
[![Snapshot](https://img.shields.io/badge/Snapshot-GraphQL-5563f5?style=for-the-badge)](https://snapshot.org)
[![License](https://img.shields.io/badge/License-MIT-3b82f6?style=for-the-badge)](LICENSE)

</div>

---

## ✨ Overview

DAO voters face proposal overload — long forum posts, opaque budgets, and treasury risks buried deep in the spec. MiMoDAO turns the entire pipeline into seconds: pull live proposals, score them across complexity, financial, security, governance, technical, urgency, and sentiment dimensions, and get a clear vote recommendation. Want to draft your own proposal? Describe the idea in plain language and let MiMo V2.5 produce the full structured doc.

## 🧠 Core Agents

### 🔍 Proposal Analyzer
Select a DAO, view active proposals on Snapshot, and get instant multi-dimensional analysis with a risk verdict and a voting recommendation.

- 7-dimension scoring: complexity, financial impact, security, governance, technical, urgency, sentiment
- Risk verdict with color-coded confidence
- Vote recommendation (FOR / AGAINST / ABSTAIN) with rationale

### ✍️ Governance Writer
Describe your idea in plain language, get a forum-ready proposal back.

- Structured output: Summary, Motivation, Specification, Budget, Timeline, Success Metrics, Risk Mitigations
- Tone-tuned for governance forums (no marketing fluff)
- Copy-paste ready

### 🌐 DAO Explorer
Browse 30+ top DAOs on Snapshot, sorted by activity.

- Member count, follower stats, proposal volume
- One-click jump to any DAO's analyzer view

## 🛠️ Tech Stack

| Layer | Tech |
|-------|------|
| Frontend | Single HTML, zero dependencies |
| AI Engine | Xiaomi MiMo V2.5 (`mimo-v2.5-pro`) |
| DAO Data | [Snapshot.org](https://snapshot.org) GraphQL (free, no key) |
| Hosting | GitHub Pages |
| Theming | Dark / light auto-toggle, glassmorphism UI |

## 🚀 Quick Start

```bash
# Clone
git clone https://github.com/huolinger010/mimodao.git
cd mimodao

# Open directly in browser
open index.html
```

No build step. No install. No API key required for browsing — bring your own MiMo V2.5 key only when running AI analysis.

## 📋 Supported DAOs

ENS · Uniswap · Aave · Lido · Arbitrum · Optimism · Gitcoin · Safe · Curve · MakerDAO · dYdX · Sushi · Compound · Nouns · Morpho · and 15+ more via the Explorer.

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────┐
│              MiMoDAO (single HTML)              │
├─────────────────────────────────────────────────┤
│  Proposal Analyzer   Governance Writer   Explorer│
│         │                  │                 │   │
│         ▼                  ▼                 ▼   │
│   Snapshot GraphQL    MiMo V2.5 API     Snapshot │
│     (free, no key)   (chat completions)  Spaces  │
└─────────────────────────────────────────────────┘
```

Everything runs client-side. No server, no database, no telemetry.

## 🎯 Roadmap

- [ ] Voting power simulator (delegate-aware)
- [ ] Multi-DAO portfolio dashboard
- [ ] Treasury health metrics from on-chain data
- [ ] Proposal alert bot (Telegram / Discord)

## 🤝 Contributing

Issues and PRs welcome. Keep changes scoped, document new agents with the same paragraph style, and verify against at least 3 different DAOs before submitting.

## 📄 License

[MIT](LICENSE) © 2026 [@huolinger010](https://github.com/huolinger010)

---

<div align="center">

*Built for the [Xiaomi MiMo Orbit 100T Token Creator Program](https://100t.xiaomimimo.com/)* 🚀

</div>
